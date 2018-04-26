
# Patches of Chart7 from Defects4J 
Total patches 396
## Patch 1 of bug id Chart7
### Patch Diff Hash-SHA-256:

bc96bc9e49297af359279314c7e9c481a64244e71fc162afafa1c1a6a1af6a02

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart7
### Patch Diff Hash-SHA-256:

d559be25bcfa448303cc549e22e1d0cb47ea386ef5e5c8412da816b0210455a7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart7
### Patch Diff Hash-SHA-256:

18d74323d496d7576ef7c735ab48aeaccd9986cb44018d2f790e5830cbc8975b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart7
### Patch Diff Hash-SHA-256:

31b79e270f121de40b60bd1ba057ac2de45585e0ffdb5a09ffb40563a1b5d04b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart7
### Patch Diff Hash-SHA-256:

3109ab1bc109fa0fc7d9bc3cbd933f587c137dbeef0740071953f8a4af2c88a8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (index - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart7
### Patch Diff Hash-SHA-256:

63c621870d5e32bc69663241313862bc7c8271b3d585316ed7ad9ebf88206c94

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart7
### Patch Diff Hash-SHA-256:

61937922dd5e87553ee04a76b3f38b9a34e571841b24cbe76c3d03ae16446488

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart7
### Patch Diff Hash-SHA-256:

37076b6b4dba03f6e6533e1c3cd4eecb0930ccf076a9ca8ef2ca570f8691e06a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart7
### Patch Diff Hash-SHA-256:

3a4508009adfcb01765b540d306973e3ce80e8a7e37e6b19f54c10581940a7d9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= ((minStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart7
### Patch Diff Hash-SHA-256:

cc4aaa052769c408f798c4ae56a50508ce2d1c89351b2296233b3cd06df93bca

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart7
### Patch Diff Hash-SHA-256:

b39de6d3e273bbdac32f1654ae8653e799e0366d21f71f07b89a71f4b8a5bf83

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart7
### Patch Diff Hash-SHA-256:

538f15d438f0b9a25b9b2cd5f602f8944e281cb0b0306c2d669f9ee90ab2a008

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart7
### Patch Diff Hash-SHA-256:

12374cbb29a3e7b869e6cbb198b8ea7302fe3851741411359985095ab5de56d9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart7
### Patch Diff Hash-SHA-256:

b05cd545d9fa836c8b3bf58e053d7c397505f8ec8f5cce1ca6dffbfab236f189

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart7
### Patch Diff Hash-SHA-256:

ca4ea0ff83c3bfc2be039a05918e31dea85e624718e44260e66d16544c942fcc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart7
### Patch Diff Hash-SHA-256:

afd3f0414c48a5eeab36916c11673df9e5462b8e5138afc138777005ad099664

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) < (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart7
### Patch Diff Hash-SHA-256:

625d5703a39fb3a8c4a59c2e9a0ac2f63d10e8959bec6a3b22bbd848605feb29

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) < (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart7
### Patch Diff Hash-SHA-256:

1b9d16d4e07390a30fbedab38bc522a93cd61b950e7720d1d10379b711d170b2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart7
### Patch Diff Hash-SHA-256:

427930ce1a4b2d2d93a429da3147641128418ed326f4e8bee1389fe241612749

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart7
### Patch Diff Hash-SHA-256:

6bfc322f8ab90b4ef4947cd892fe5a99e1e3cea3c0d3c577fb5519d6f7166821

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) < (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart7
### Patch Diff Hash-SHA-256:

ec3f3dd05b7daf637c707ca50813b598d20e64e70b9e9c1ba6dd66ccf3c6d303

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart7
### Patch Diff Hash-SHA-256:

1df65bc15b799b5e0d2935c444cd736cef1ac6834da66812ce4a70017c4a60bf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((minEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart7
### Patch Diff Hash-SHA-256:

8aa4134f77fa819b7832e6a857a9ec256a4b5354d40ed87f3d424f3e1bc9dd99

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart7
### Patch Diff Hash-SHA-256:

73e17c4e9e6914589b58e0b56e9c1be2565177ef91752e128938c70758733c63

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Chart7
### Patch Diff Hash-SHA-256:

f954800922023ec0c6b26cb41b266cad4f5c31542ac1340ba85be30b7cf31472

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Chart7
### Patch Diff Hash-SHA-256:

73cb5a994c478973eca1ff865319467736f06ae78d007138e010ecd910610de2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Chart7
### Patch Diff Hash-SHA-256:

b675be468e9ad6f46f2c5b625f681d2b4f09e415477aeb6f02c80169537c794e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) < (maxStartIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Chart7
### Patch Diff Hash-SHA-256:

4398d840b4aede73ae7f64a81fe2ae8900e5800ed90982d1c34df5be158d5a0d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Chart7
### Patch Diff Hash-SHA-256:

e2386b3adc43263dd4ef22aaf17a2958a84740ee30d4f63da9ef3b7169480c7f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Chart7
### Patch Diff Hash-SHA-256:

5c82717a72cf043fb4e24cddd93653a71fc45120eb35a7c82e267c7d566f9be5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Chart7
### Patch Diff Hash-SHA-256:

34cec1fda16a10710ac2b9ded1d92b165b418254275c2ed08fdf86df4fa78c6f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Chart7
### Patch Diff Hash-SHA-256:

ad956ff64a1c2dcd19709c67ee7e3596201ab9aa3717cd8571c4170d1c0c8597

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Chart7
### Patch Diff Hash-SHA-256:

cc175934948ea2ea3d37822dcd8084ef5faa56e7c0c15efc855e1a411c3b052c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Chart7
### Patch Diff Hash-SHA-256:

485ef52a859411979f8837954cf91ab4b0d30f0e68d8aadad9b773322dc34758

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Chart7
### Patch Diff Hash-SHA-256:

493244d941480cd9279ea676592f9db1bde4ce673c9e8d438b51248e4030699c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxStartIndex) - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Chart7
### Patch Diff Hash-SHA-256:

f9717a8b4e2d9b2dffb7396d1b1c489e75792efcc58bec227e9d3ed600ab5ff1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Chart7
### Patch Diff Hash-SHA-256:

b94488bdc5e5bc5409d822352a8ee1a00ec5b3394f2696411042b014977e356c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Chart7
### Patch Diff Hash-SHA-256:

d6904db394bff1b533b75919836a54d22d1ebc96837639ecef8a485065cc9066

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Chart7
### Patch Diff Hash-SHA-256:

2616aa2a7987a333882d79709fcd40cd7665f394c07f1ca0bc6cde9bf19ee4be

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Chart7
### Patch Diff Hash-SHA-256:

5e2751d1fa7b1d63fdf7799f734f4fc16fd736fd1928dae5208a8f82149ac739

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Chart7
### Patch Diff Hash-SHA-256:

43f9ee715ef1048780d94c086f0672f64a6b526082c14fa5f47d72766145e40a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Chart7
### Patch Diff Hash-SHA-256:

381b75446046e11399aa22e6924d383ffbddca1a4728ef1c25efabf1bbbc28fc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Chart7
### Patch Diff Hash-SHA-256:

6412a9c6e8565ee4cb8130b24b0d45275de5cf4678d5aed67f2dc667448a3794

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Chart7
### Patch Diff Hash-SHA-256:

2262d96f01eb4dd3f5d0395b267d0991d94247c63ed4b06a5ba64f99ea5c23ed

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) < (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Chart7
### Patch Diff Hash-SHA-256:

1188cd37b37eb750b62c83dd7e6497bafbdb8728440ff4573288fbd876cf20ce

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Chart7
### Patch Diff Hash-SHA-256:

d6b4bf7d45a3d2f3fefb2800091186700011bbee1ea2e8a6581d5167f8e6e5b3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Chart7
### Patch Diff Hash-SHA-256:

d1518a897a0647015cb9a656aa7f76552818b43995a662038c0e80bc5980c5c3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Chart7
### Patch Diff Hash-SHA-256:

804e93878d3fabc2f8b8e31fd261b32504c05dbcdd7b710a09f679b4b24b5c74

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= (index - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Chart7
### Patch Diff Hash-SHA-256:

e72d302130087b9321595d422df2faee5698eec31e47cb4d8dadcd6b15cd4c3e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (index - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Chart7
### Patch Diff Hash-SHA-256:

bf9024eba9c1d0e9b2c0683bda748978a7dec48cf86710a53affaab60cb650ab

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Chart7
### Patch Diff Hash-SHA-256:

90df187e2ed9886b14aecd05c457e6c55581eac8eeadda32174297452c957c24

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Chart7
### Patch Diff Hash-SHA-256:

bd0f3b0e14198c7fd3ca0f1ca956113e5cb358b6576419f4ecb6a4e3ae75578d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) < index) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Chart7
### Patch Diff Hash-SHA-256:

798957915ef4861b2e7d217734d547a924c87403eab839e3473f25a11f195270

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Chart7
### Patch Diff Hash-SHA-256:

9180df2ef66e09e2cbcb2304134b923d24b730074a3dbbe7612f015a3e4d5ca1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Chart7
### Patch Diff Hash-SHA-256:

075aede5ad87eed74b589f5c335388f1de24a900a71f3215c97526568019019d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Chart7
### Patch Diff Hash-SHA-256:

4ea5ad992e3da8b532ef07a839b06676a2e4183571e243ec722af3fd95c6d86c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= (index - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Chart7
### Patch Diff Hash-SHA-256:

1969d3ee4c01052aa5aeb3b009312472c1250882e3a4d94834e51385f190b7ee

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Chart7
### Patch Diff Hash-SHA-256:

8f95941fd4770cb5ca24408e127a58a0ae5175d0db4db5b53fe688eb82e39363

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Chart7
### Patch Diff Hash-SHA-256:

3c2659d9bf40d434d512498cc3e7207ac607245886309c65709ee51713e338eb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxMiddleIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Chart7
### Patch Diff Hash-SHA-256:

9830f2f9660d396939d94d2076746ee94780e65d25932d2893846e67794de05a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Chart7
### Patch Diff Hash-SHA-256:

72035fe07cf8b9f10620128b8cc5fdf82b04938a4785337aa2787bff0bc51c9e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Chart7
### Patch Diff Hash-SHA-256:

cbc1ff8942760048ea18bbff129a17679857dfccb782d560dda8f819979d38cd

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Chart7
### Patch Diff Hash-SHA-256:

415b1acfa237d58b69b396864cc6c8402a47f142b10fd35109e5f1a1f38087cf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Chart7
### Patch Diff Hash-SHA-256:

2d3c59634c088a4a00f4d683b87133b03f637f5513bf90235a09325299895ba4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Chart7
### Patch Diff Hash-SHA-256:

761c65bf2fc02b6782b927c3c55563dc9adf02d11e21d1e92329d7bcb893941d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Chart7
### Patch Diff Hash-SHA-256:

9a58b71bb573741fe9a327968bd1ce2c4e218c1ca7b1f472a06c177e9c6b357d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Chart7
### Patch Diff Hash-SHA-256:

9f8da5163e14c4a5cd11baf7dabca00c6e1b0ac49cdc2fb9525c278753ea6d1c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= (index - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Chart7
### Patch Diff Hash-SHA-256:

a0499a3dce8410f3e9f2dc130f3e8ac94e2df7755034536d3ba7d2d49c34d9d5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Chart7
### Patch Diff Hash-SHA-256:

d810508e5fb6db7de8fea8fca113fab8b12762af698f56a5c5faa7244edc9096

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) < (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Chart7
### Patch Diff Hash-SHA-256:

5dc7a0b995482120333fdfdd013628cdebbd3a903703a6b77e11ac1fb41965a9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Chart7
### Patch Diff Hash-SHA-256:

b6a1e30c429cbbd80a3bf4006bec0dd9beb100905965aecdb3a1a7f7815843d4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Chart7
### Patch Diff Hash-SHA-256:

c9ba911fac4546f9c0f43801e9eeb54a5b0fbda315a7f6ed091e88ed73f13f38

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Chart7
### Patch Diff Hash-SHA-256:

1691119c6dcdf368fa6df3fb6f1975855e3998300d33842cf40d61920f4d4626

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Chart7
### Patch Diff Hash-SHA-256:

d3558729ec3e833676dfe6d0c591bb7a7d33ffd6a3a7e4822ce0c1d0ebbb7751

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Chart7
### Patch Diff Hash-SHA-256:

4866da4776af67e82143309740d748e7eb425fca9b3d401f41c782251968414a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Chart7
### Patch Diff Hash-SHA-256:

8c7933004ea0ae0f2bb4ad5213e405b5400a5c17f664cdd46d661b5e0a6d7ab5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= ((minStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Chart7
### Patch Diff Hash-SHA-256:

5d3051d7aeb73ce73c36daf5b2cc88d9eff65ac40fa28df86bc17bb1dfdb20c0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= ((minEndIndex) - (minStartIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Chart7
### Patch Diff Hash-SHA-256:

ce3e780da35108459761f925423215ffe01097d40b81fa73b83046ed90bf69c5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (index - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Chart7
### Patch Diff Hash-SHA-256:

5bf8ca8e94b63844d72f44166b6a3a4dd2c356c4b474ff5afb4b17974b6fc834

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Chart7
### Patch Diff Hash-SHA-256:

1e83d1e2014fe4f93ef5c6370ec58537aaebd0ed0599951eaafca4098e5b499f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Chart7
### Patch Diff Hash-SHA-256:

697fb03f7707c4e6fc17dff6583eeb117f55e380392a1ec80f5e7c723cd004a7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Chart7
### Patch Diff Hash-SHA-256:

c2ccdf90da84abbbaa07eb369854d214f25ae0f3bcb2aebf053e888022b34d3e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (index - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Chart7
### Patch Diff Hash-SHA-256:

f6126f472dff5ce233117e96e85ce55f991bc1dc49266131eb8b9aca8625ca40

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Chart7
### Patch Diff Hash-SHA-256:

a9f06a97319f095001e7f03ef3a62d64f7d21f6271ac3595c5a55e2a30a7b8ac

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Chart7
### Patch Diff Hash-SHA-256:

b0142c1d4b229ad13eb82f23c31da8f906c24322bf19b76d5bc63c27293a8929

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Chart7
### Patch Diff Hash-SHA-256:

947cd2bcf71dba6733f6249fc73fc2eb94e37b32debabf4342d49c508e9660e1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Chart7
### Patch Diff Hash-SHA-256:

63545fbe5020556e6c536b5bd4ae81bb6ed6d79bbd69bffa7174a6ab0f1caefb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= (index - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Chart7
### Patch Diff Hash-SHA-256:

34ce553d000fec9c8f4a4338ee97a483163bf18826e6d0a13a6d51818c2610a7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Chart7
### Patch Diff Hash-SHA-256:

faf0e4b9635222b211a5bfb3affc37f06e4861bc61595e7ef2629160b409dca5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Chart7
### Patch Diff Hash-SHA-256:

7ea91720b051b84075a14510c5ccfc07606e152e82ec60337ea85c16121af18e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Chart7
### Patch Diff Hash-SHA-256:

86243c27c1723422da64e59295d818cbb5903394144b4d3916c7efd199f7e3c2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Chart7
### Patch Diff Hash-SHA-256:

b833f173dd12febd37940f9d2b03518997ffa898c78255c227f612c3524aa595

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Chart7
### Patch Diff Hash-SHA-256:

5b12ec823291d7ac3e1d0b30985b662b6d4150aea0b2dd7d6ccc29bf5f732fa5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Chart7
### Patch Diff Hash-SHA-256:

7c966c3c61b656d89bbfdd0ebb9c6f0f70b980e950a2f8c3e50561946a234122

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Chart7
### Patch Diff Hash-SHA-256:

0df70fa1401dc29cd0b97ee0195986ff54b79ef20fbdc48b2e379fc76a5f93a0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Chart7
### Patch Diff Hash-SHA-256:

93cfed47b007c79c617366fb1ea2325ea22351127f29f3e3897e1bbf7544b810

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Chart7
### Patch Diff Hash-SHA-256:

c7f2fe7d58a7bcbdf43705efc35deb2cc75089e3f1b6d3fb46755c1edaa8a1c4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) < (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Chart7
### Patch Diff Hash-SHA-256:

6b97614315f3ad2329a60955e37e1316436622b9f7d88ef6ba5d96072e38e219

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Chart7
### Patch Diff Hash-SHA-256:

e986ea370aa80577475852089e68dd3c3682ae1ca951ac7667dcad6735508b0e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Chart7
### Patch Diff Hash-SHA-256:

f115a1ee50c94b7cbf3c000e01973c2919924b9ed55d1134dcf383888d678c5b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Chart7
### Patch Diff Hash-SHA-256:

4d9ee46339b541b8396cac0372f94b0b46fd9688d83ff326ecfeaf5ec9414954

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((minEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Chart7
### Patch Diff Hash-SHA-256:

7870f07f7393dc9382afb600ff6976e43765e0671e58e9a307ae47c1fe16c5aa

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Chart7
### Patch Diff Hash-SHA-256:

faf519be37f069e417e0a14b3d38edd8d6a500ff1166ab7cfe1b848e12ecef70

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Chart7
### Patch Diff Hash-SHA-256:

83a5d7dae12a1afb0d7a6433bdf5e5ea915e21e8efbebb1e999c484dac9b32f9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Chart7
### Patch Diff Hash-SHA-256:

a599782a08a4f0db27d4ddd08de4c2511a218be7bb69036253a48ef39e2c2448

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Chart7
### Patch Diff Hash-SHA-256:

7517eeeefc81a5c2f3539ca2d15ab6500ab500f62f7df7893dc17e69e4092032

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Chart7
### Patch Diff Hash-SHA-256:

f925db83a0229c53761858c52d28e335ed5b5dd79a1d3f21b131a54831a51398

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Chart7
### Patch Diff Hash-SHA-256:

fa2e72ad50f3dcc4a3f482bd1edf699b9766feb1c555223a3d6061d5e9f45159

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxMiddleIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Chart7
### Patch Diff Hash-SHA-256:

de3570824d0443545c463f1faefb79de3898824213df3826923fd10005d5f588

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= ((maxEndIndex) - (minStartIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Chart7
### Patch Diff Hash-SHA-256:

4cb3a1d712c2fd380a5b2c8e4da67d7c5bb47030290037617ec3749fc14bb683

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Chart7
### Patch Diff Hash-SHA-256:

a3405f8064fa334885b047118461ceedcaea7fea6840a94d3ea8ecfdaeb51fb7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Chart7
### Patch Diff Hash-SHA-256:

8bbaaa31626bd7217414c6b38b153742b7de1f2cb5fe3dde7bfdbb7e041496dd

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Chart7
### Patch Diff Hash-SHA-256:

c29901ed4ef0d9f2380e27d6c954ee0cca587930cc1a3f1162027896d98c0f01

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= ((maxStartIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Chart7
### Patch Diff Hash-SHA-256:

88b7942ddf8987d40a0b164840cf616d00a23afa550f53061d0e71c2de393c54

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Chart7
### Patch Diff Hash-SHA-256:

623a741fa684ce86b77cf06fe76bd6e465ac799d12817cc593100ed2c79e359c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Chart7
### Patch Diff Hash-SHA-256:

10aae6c7c05d95c5168ac3e7a0d515080364131e6e82ee29c4ba084e32d2a857

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Chart7
### Patch Diff Hash-SHA-256:

f3deeb81992b0d99c2b7b62caaca4deabc7467709a0477095eedbc0a8c744570

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((minEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Chart7
### Patch Diff Hash-SHA-256:

aac64dc713ac87b17caa0e5d84506e071efc260110234210156cb78d17ca198b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Chart7
### Patch Diff Hash-SHA-256:

e64ea0d1fb52b2ab015d6c12d3297eaa3f27189db37f6da0b6954c29a7980252

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Chart7
### Patch Diff Hash-SHA-256:

76ab992a146806b06d55fa433560321c833d0873e627955fc337c176a55b111f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (index - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Chart7
### Patch Diff Hash-SHA-256:

65a9be7b13dceed9cc78fe6e857044261bb9214604f62fe8138ccf7450bf0e4a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Chart7
### Patch Diff Hash-SHA-256:

6c76779296b9c4fea0158eade973f1478c89e9076958bb2941e8c0fab013f96a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Chart7
### Patch Diff Hash-SHA-256:

593cf4e7ca950e1918a3c15ca2009b387bea35d0339252795e36f9c656c4b6fd

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Chart7
### Patch Diff Hash-SHA-256:

24bac4739cdcc803131216d1b6d500acb4bfb4fa44e16f13ece5ca908ed99580

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= ((minStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Chart7
### Patch Diff Hash-SHA-256:

b18afab45eb9fb600fbec8189110ff88c389d2384cb0e3111f1b3547e0226172

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Chart7
### Patch Diff Hash-SHA-256:

c44bb8043d8358eb49c2ab003abbd79d69ccadbf5839c0b411e00f271bd5c24d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Chart7
### Patch Diff Hash-SHA-256:

f98a5a6b25da4d3125b5e378a106e6c9dfd7a9ccabf15a3758c3b9a413f08d82

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (s != 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Chart7
### Patch Diff Hash-SHA-256:

6cd2778aaebf99a90654c6f99defa4530d16a9295b11ac17c9b8d14d34fc71f5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((maxMiddleIndex) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Chart7
### Patch Diff Hash-SHA-256:

59864ebbcf835cb851e7192185fd0f888599ca467cf937c6f31835d03821fe45

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Chart7
### Patch Diff Hash-SHA-256:

0afc94d9ae43a5d09e17ca0d7967cccd1ac8fc91598f2e90e01696e99e72ed81

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Chart7
### Patch Diff Hash-SHA-256:

9908309015646773c1b41295b4c4723928e61cfb2fcd3e6f455050e321599d78

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (org.jfree.data.time.SerialDate.isValidWeekdayCode(maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Chart7
### Patch Diff Hash-SHA-256:

b3497da1377fac7d156d5c80a0b8c9894c4359b0d720e3124f0d27b5dc80a2ff

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Chart7
### Patch Diff Hash-SHA-256:

92b8685059706de7759aaff9734ff9bb62fcc696ac9549b912460784f4c60164

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Chart7
### Patch Diff Hash-SHA-256:

7c0558b48b8da58ce35daf91eff529d5ffe7bb812e8815ff9bd21338198a6495

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) >= (maxMiddleIndex)) && ((minMiddleIndex) < (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Chart7
### Patch Diff Hash-SHA-256:

b286c8f7f08555ab683eb3e361e3627ba616b6202f61f9f3759d475785bca1e7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Chart7
### Patch Diff Hash-SHA-256:

cf512344bd0316cdaa6079149f6a9bbef14bdcf29d306470190c201236522ac0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) > (-4)) && (index < 2)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Chart7
### Patch Diff Hash-SHA-256:

ea2d64dd7074f72afbe9a790a04047f428aa9d4129095231d770e3b76ba6c227

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((0 == (maxMiddleIndex)) && (0 == (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Chart7
### Patch Diff Hash-SHA-256:

0d976d2cd88bccb28a19c66ffd58a069692fc79a1e10672610d7a75ab0cf7c3b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((0 == (minEndIndex)) && (0 == (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Chart7
### Patch Diff Hash-SHA-256:

0952e56ab27922d4287242f432270d014268c6934bea0a039e97ad606eeff721

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) == (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Chart7
### Patch Diff Hash-SHA-256:

56f3360d12eecf6fa92ece4060d9c1670e18045163e8eeee8b4e5fdc7520b9cb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((((minMiddleIndex) < 1) || (((minMiddleIndex) < 1) && ((minMiddleIndex) < 5))) || ((minMiddleIndex) < (4 - (minMiddleIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Chart7
### Patch Diff Hash-SHA-256:

e71078e1abc33a2ed936f44f589a95e106ab15a3dde73cca67075a4049048929

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((maxMiddleIndex) % 100) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Chart7
### Patch Diff Hash-SHA-256:

b3ec06cb011c44de386a6f077e9e0543173a291a39175b805a705ffc34ff1794

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) == (minEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Chart7
### Patch Diff Hash-SHA-256:

855c74719ec8e230af63849e2502ab9fc92a90b19b95a01c725793c691200f46

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) > 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Chart7
### Patch Diff Hash-SHA-256:

2418aa9a8a75ba1c72c1e767562ebc42fd405fe541e6dd2382354285a2498b0b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (index == 1) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Chart7
### Patch Diff Hash-SHA-256:

2bdc8791d0b5a981ceb0890137af017575a11ea0d0c12ffd7dfdb7b663123498

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (org.jfree.data.time.SerialDate.isLeapYear(minEndIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Chart7
### Patch Diff Hash-SHA-256:

2122a1610f95df14cff8aa86be5f11035f2cc3d26a92ad435e77cb72c9b31299

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) >= (minMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Chart7
### Patch Diff Hash-SHA-256:

9b668ee3c90b4a1c2c251e548cf0a081750f95e361949ffa0a52f78b10641c76

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Chart7
### Patch Diff Hash-SHA-256:

2b7c8fa1abca7e6595655474941f40e71f7aab218d5faf8c5649cb6b9c3e1eda

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index == 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Chart7
### Patch Diff Hash-SHA-256:

8fb06b7ce4234c36d691ffa5de32c0765b9f339139ea83af9eda5aa6447d2613

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) % 400) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Chart7
### Patch Diff Hash-SHA-256:

573cf376288cac89d9035d0702dfc86ebf2fef8953bb5282ddbb59794b3a8312

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minMiddleIndex) % 100) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Chart7
### Patch Diff Hash-SHA-256:

ce7da69652b13db5691e586b2fdc653cba9fe053ed20dc3c073d80d9c32fcfc2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index < 2) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Chart7
### Patch Diff Hash-SHA-256:

d11d81d0a6c19441c197f0ba5c117d820edbecf675073a5726b7c8da61b5c077

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (!((0 == (minMiddleIndex)) && (0 == (maxEndIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Chart7
### Patch Diff Hash-SHA-256:

d41817268c17ac0d0e994e66bf046a090d8d964f7db82747c508df2c7811b235

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxMiddleIndex) % 4) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Chart7
### Patch Diff Hash-SHA-256:

e6308cf3fe5d76ceab81d3120e546aea907b327a204b3d172eb59bc75fda8315

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= (maxEndIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Chart7
### Patch Diff Hash-SHA-256:

b3f31a3c72d24d969d5f3d7c49645cbdb7ba51f82cfdb55aea53538e3b88b6d5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) < 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Chart7
### Patch Diff Hash-SHA-256:

f3b987c6175099350f03d41f412b4470faaf33e78cfb659ad1ff686de029b292

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minMiddleIndex) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Chart7
### Patch Diff Hash-SHA-256:

9eac5e4ba1364537261cb36f9eed50472f3b462ed01717e0ec84125a36b94bc8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) > 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Chart7
### Patch Diff Hash-SHA-256:

8340a6eb183647a762e429b9d9a2d8ccfef9355469cea805a7aa70fa26738577

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Chart7
### Patch Diff Hash-SHA-256:

d0b7de9b7293f3278f7fa1b105b21ec2e2dfe62cbe0ae2a67aaf03d49cc1a4c3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (org.jfree.data.time.SerialDate.isValidMonthCode(maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Chart7
### Patch Diff Hash-SHA-256:

e6f6770f29b692133f65b28ec3d94e0b0830886090fa22124159c3a727499414

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (org.jfree.data.time.SerialDate.isLeapYear(maxMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Chart7
### Patch Diff Hash-SHA-256:

b471a34c0cfc754fa9569b32994407ce6195f27c35c1876b45ee0c1a2862779c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < 0) || ((minMiddleIndex) < (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Chart7
### Patch Diff Hash-SHA-256:

6eef38b312c8bf9333c781736b998f4cf289980e6480066542a4730e97c57396

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) == (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Chart7
### Patch Diff Hash-SHA-256:

59edc909f43f1f5ada6699f2ce51d2adaf006e3178b353f564408799a3b87d1f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((maxEndIndex) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Chart7
### Patch Diff Hash-SHA-256:

9b2cb3a07a7b858c77ab7f1e718e1a35592649f9f4c83fbc541363b4b48d5307

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (0 == (maxMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Chart7
### Patch Diff Hash-SHA-256:

230f323e3100c8088e68786e6a2ddddd34e715a279a3379fa67987b83a4580d1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) > 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Chart7
### Patch Diff Hash-SHA-256:

84c497279f3603afa40fc30e23ba9a8506995eceba5f9dcc49a3691f50a08e97

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) < 2) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Chart7
### Patch Diff Hash-SHA-256:

f91d243bb2f9a4510432299071b114b56f5ea8f5d9f45b690e52944ab0c6c6fa

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((0 == (maxEndIndex)) && (0 == (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Chart7
### Patch Diff Hash-SHA-256:

bff65cd57b11583f32f4e32d22e850c240933de1997f62b16829b5afc3966271

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || (((minStartIndex) > (-4)) && (index < 2))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Chart7
### Patch Diff Hash-SHA-256:

fb5e7c84d2946bb5c2efc88faa32a81adcb076f3cf8c64e8af5c6195203b4f68

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) == 0) || (((minMiddleIndex) > (-4)) && ((minStartIndex) < 2))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Chart7
### Patch Diff Hash-SHA-256:

ad18968ae9f7af7ac49c6e72b717023a315a1cb256ef0e0e65155aed48391901

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Chart7
### Patch Diff Hash-SHA-256:

4075420ffcb6157e8db856c7b6c8a336f597b3b70c89f36b864a1301664c955c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) >= 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Chart7
### Patch Diff Hash-SHA-256:

3bd60f96b5a9c9e57e6f67ec87889dbde211f4e0e2374a78d305b45739375429

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) != index) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Chart7
### Patch Diff Hash-SHA-256:

fada604ceee934f5d087bb12d2aa5c67d252b6e342ae09381b1e3d7596839b15

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Chart7
### Patch Diff Hash-SHA-256:

9d4cb39985a8ca5d25c38723b1d337222e3028d3ef15c3d498321694a8b5f96a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Chart7
### Patch Diff Hash-SHA-256:

d2e4144fdf81d77f31a3adcc32d6588f676a7ada17ba989d5e880fd9a6b0e8e9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < (4 - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Chart7
### Patch Diff Hash-SHA-256:

cd2714e9bf56be78c0c2ea81630b49100a235e0df19da30193a1516d392a4fcd

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) == 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Chart7
### Patch Diff Hash-SHA-256:

ea1cce8b14257679f304b4357fbd1ecb59c92cc493c02814dc15e66d826cd2e7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) != 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Chart7
### Patch Diff Hash-SHA-256:

ecc3e60c2fe77bea8316e3e592abf86117c181c793f943f6b840ec643029ea3c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxStartIndex) == (maxMiddleIndex)) && ((maxStartIndex) > 0)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Chart7
### Patch Diff Hash-SHA-256:

654d7e731783a2a4c70cef88ef92c784b8c7b52c1b0f917a7af5fb14115603b9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) == 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Chart7
### Patch Diff Hash-SHA-256:

7e4f8407fcf6985318d05d27304119bc29c2520be348f653968b3ab852433183

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) - (minMiddleIndex)) >= 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Chart7
### Patch Diff Hash-SHA-256:

ba5d7754e269034114628ba489988828da7e6b1c5bb07cb9c861ed222b7d7962

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) < 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Chart7
### Patch Diff Hash-SHA-256:

fbef9f4aa5a78b1c4eee1c16408c292867c19ec6aed162a25196f01c5cc28a8a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((maxMiddleIndex) == (minStartIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Chart7
### Patch Diff Hash-SHA-256:

c9a26a3b9488c52a9ab11f0760eeecc84bd083f85f94179d4541995421dba184

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minEndIndex) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Chart7
### Patch Diff Hash-SHA-256:

0a027483d55435a82b6a1015959f6f0e7b7c19b7ff0c54ed3b166a9a8e34ecc8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (!(org.jfree.data.time.SerialDate.isValidWeekdayCode(minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Chart7
### Patch Diff Hash-SHA-256:

c06b526c68671487f01966088f6070732743c8b3fc5e00b6b9f9320f5145cf72

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Chart7
### Patch Diff Hash-SHA-256:

b8078e000b60ed6da1f563719afbaf00ab07573a7a9e668ce1c4873757edf1d1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) == 0) || ((minMiddleIndex) == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Chart7
### Patch Diff Hash-SHA-256:

f5a76128f5831d1cf0cd7de7bc0fe4476e686117f4b4eea5621b9201491a0784

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Chart7
### Patch Diff Hash-SHA-256:

09ca94273848c4bc601dc99be00086977cfcae4f112acbce22d5844181333cde

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((minStartIndex) * index) > 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Chart7
### Patch Diff Hash-SHA-256:

48c77cbfde9b9f9f94ad7a62b01d6056e3157fa8e2df7771e247e72f601ebfe5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Chart7
### Patch Diff Hash-SHA-256:

3b2f1740b412f4f2cbe4ca8773bdb4dde1096eea97ee8dfc4833dd17ef9a947b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((maxMiddleIndex) % 400) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Chart7
### Patch Diff Hash-SHA-256:

d3cf50d56e367685abe1afde74090a2be64683994f5c194e82c07f84b2172cfe

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Chart7
### Patch Diff Hash-SHA-256:

26b3d722f74cfcb60f11ffdffb209b7fb855ef176dfdd606f099edd6bdc5bb14

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxEndIndex) % 4) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Chart7
### Patch Diff Hash-SHA-256:

b358b88c20dd1dea4dda28e457b74428aa44f27dd345c2a7752340ca9a8b6ebc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) == (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Chart7
### Patch Diff Hash-SHA-256:

8135b31cbd46656e1f662afbee081cc6ab564e9c550d6fe23f3ad742f8da96f4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index > (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Chart7
### Patch Diff Hash-SHA-256:

f1c3bab3eb1eae4a91c928e75cd001d19690c5548a35412f8de79e2fd961dad3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) < 1) || ((maxEndIndex) > 12)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Chart7
### Patch Diff Hash-SHA-256:

a19102840f58283510c7653333d712efaec9df7c7f61c7033f31f90c7aad3ba9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index > 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Chart7
### Patch Diff Hash-SHA-256:

f764396071f8f0ed26a9dd68c4e4eac0a1ead5b5f0dd95ed6ba36d71e7beffc1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (0 == (minEndIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Chart7
### Patch Diff Hash-SHA-256:

29ee8d76fbcaa1046d955d4d212fd017fd72d3dc1cc3d5ada583189c9d4cad8d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) >= (minMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Chart7
### Patch Diff Hash-SHA-256:

93367a545aafd2011a8244cb29f625d59fb2d41f9849a5781d84160a5dcfc6a3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < 1) && (index < 5)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Chart7
### Patch Diff Hash-SHA-256:

fbf0280968ba0f47100e949891cb533b2a0a93605d4bc9e8f9cd53ca2054c5b2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((maxEndIndex) % 100) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Chart7
### Patch Diff Hash-SHA-256:

57085644d08fd54b2322cd5d3324235d740020b4568db6e4da720f231ecaa01d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) == ((maxStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Chart7
### Patch Diff Hash-SHA-256:

6af413c00596080594f68e29b8f366872328764d7db39cf4900e8d414a2061ac

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Chart7
### Patch Diff Hash-SHA-256:

9eeb5c98178861722cea7bb3c0cefa5586c3271e362ddb255aba673289e91079

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) % 100) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Chart7
### Patch Diff Hash-SHA-256:

37c7f52eb45d579f0d5853e8a3101a8ff1c3f7ac979a2b050791e4beaa01015e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) >= 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Chart7
### Patch Diff Hash-SHA-256:

c16bbeeada703ac1ee97ff47e037e005116d73293293b3c30c937dee1ded2d0e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) == index) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Chart7
### Patch Diff Hash-SHA-256:

c6b4dc8c85594ce440781c3512fe83eb8b6fb5009b156b6c4015aa3d1fe4e07a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxStartIndex) == (maxEndIndex)) && ((maxStartIndex) > 0)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Chart7
### Patch Diff Hash-SHA-256:

4fe21084bf55df8532d6f11e6e829ec6ad2e592bcb58fc29e88cb0066c68ba6c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (s > 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Chart7
### Patch Diff Hash-SHA-256:

cb2425b209ed21eb80fcf81bf29e2a6e038f261fcdee9cd8ef46d1956d09dd1d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) == 2) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Chart7
### Patch Diff Hash-SHA-256:

f2a18d4c804181f441b9967d129b4363d19dabd6f7ff83edace34b261ff1bd21

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (s > 0.0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Chart7
### Patch Diff Hash-SHA-256:

16db04017ca00b61cb04c1e24eed89b1897d0966e5fc8f0ae7c7475d98c82055

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= (index - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Chart7
### Patch Diff Hash-SHA-256:

1f55dca6c7848d40e66b1c78d54ddad6eb1c4a9b31fda6c60b92a686dc7bade3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) <= ((minStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Chart7
### Patch Diff Hash-SHA-256:

d1922387c420be39d4e7bba3245b0d6fe79d73434b6c15d6e1376045783d9809

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minMiddleIndex) < (maxStartIndex)) && ((minStartIndex) < (maxStartIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Chart7
### Patch Diff Hash-SHA-256:

32c0f662993c59592a248184ec307f3edaec62e6b5f846a92f55f64203403d00

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < 2) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Chart7
### Patch Diff Hash-SHA-256:

4d999b74dfb31a82a30e1a0059da21e414e0fd3d18e3b07ba899c8a2b377af5a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) > (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Chart7
### Patch Diff Hash-SHA-256:

ff301e9175f627676b7c1f1e993a093b86c5b00f1ad5050c0e3cfbc502071385

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Chart7
### Patch Diff Hash-SHA-256:

a81f62370298bde6a02a234ad7925a59007f190efa48e1980a21dc825df0fafa

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (0 == (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Chart7
### Patch Diff Hash-SHA-256:

b4180ffa10b8224816824656bb99b3cc82dcff002857bd7dff2b528471c0a825

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) > (-4)) && (index < 2)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Chart7
### Patch Diff Hash-SHA-256:

6e92f8bb628bf2a260b0b4cebee66b94419dbc5fb36a7d7e2629badbe1cd19ba

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((0 == (minStartIndex)) && (0 == (maxEndIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Chart7
### Patch Diff Hash-SHA-256:

6799008cbf51f397ae0a75c38137d56d7d2c098d3ffb98305bbcc1a5b15f51ba

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) % 100) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Chart7
### Patch Diff Hash-SHA-256:

fa5e13923fe66468f8652ad3cff2d61a3177b1665fbdcdc9621d1d52e195db2b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) < 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Chart7
### Patch Diff Hash-SHA-256:

279f43aaaff543a74a61fe01642b5ae22fdd564e8b6e25db0f698a6a5ee5839d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (0 == (minMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Chart7
### Patch Diff Hash-SHA-256:

34d7dd07a3c1b646826e7c3bae2018ca73fcae54ae1b9fe30b2698734be600d3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (!((0 == (maxEndIndex)) && (0 == (maxEndIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Chart7
### Patch Diff Hash-SHA-256:

3c2de67fb18b1ec365c9244b85350dd686f068ff9144d25bb506cc5d9d69f1ad

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (org.jfree.data.time.SerialDate.isValidWeekdayCode(minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Chart7
### Patch Diff Hash-SHA-256:

28000e3c3100e95982e0a2cd5c66a4feb650f63e6643cddf0fa140975206badc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) == 0) || ((minStartIndex) == 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Chart7
### Patch Diff Hash-SHA-256:

89090d630ffd5719b4f4ca1b93155c7183d779c2011eafbf16371c26cbb5270f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) < 1) || ((minStartIndex) > 360)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Chart7
### Patch Diff Hash-SHA-256:

b73dee160d33e40994cba39a094c57cd2ef437d0eb0e06edf63ed5f31c9178d1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) < 1) || (((maxStartIndex) < 1) && ((maxEndIndex) < 5))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Chart7
### Patch Diff Hash-SHA-256:

061d8e84847e28e906883ad2c0829eee2c9fa1d8454fed6ce24c6c45caaf2b7f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxMiddleIndex) % 2) == 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Chart7
### Patch Diff Hash-SHA-256:

bb5a683ea8ebc9e5f60ad0150d1a2b8144f05786e8feab4d7c59ed9ee158a255

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxStartIndex) != 1) || ((maxMiddleIndex) != 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Chart7
### Patch Diff Hash-SHA-256:

cbac070e36d53af78e76f3bf1917e4f7b35ac386926e31db130d226d2148781c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) == ((maxStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Chart7
### Patch Diff Hash-SHA-256:

be732dcb8a87ef2b91c776096f04d3f2e935818224b3dcb61499374c560dfa89

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) == 0) || ((maxStartIndex) == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Chart7
### Patch Diff Hash-SHA-256:

fb9b8de2e3f73232c7643ddc1ca39c613a1e57ff728c728116c907f970c2dd63

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < 1) || ((minMiddleIndex) > 12)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Chart7
### Patch Diff Hash-SHA-256:

f151e877447482b478ef9c55e169b45b54449395f663eb1dfbfde58879248c0f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxStartIndex) == index) && ((maxStartIndex) > 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Chart7
### Patch Diff Hash-SHA-256:

48b480e2a98fab7a886c50a817ab6f9b50ebf2b00fa78c03e6e746ffee250ecf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minEndIndex) % 400) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Chart7
### Patch Diff Hash-SHA-256:

b9499b6e30b91e844a4a5f47b058e66d679ab60990a22f69671d1b261ae75168

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) < 1) || (((maxMiddleIndex) < 1) && ((maxMiddleIndex) < 5))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Chart7
### Patch Diff Hash-SHA-256:

ce7f7b47642e682b151725fff623539ab190329cde54efcaf8dcbac3400195ba

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) < 1) || (((minStartIndex) < 1) && ((maxMiddleIndex) < 5))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Chart7
### Patch Diff Hash-SHA-256:

f449efd6285ffed6fb5c96d19f7a2b874f630b3c966313e74e029e607b494341

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) < 1) && (index < 5)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Chart7
### Patch Diff Hash-SHA-256:

d08162156183cc96f201f5db881b4094373da17da124ab9c3221c81eb4bce0b9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (0 == (minMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Chart7
### Patch Diff Hash-SHA-256:

1002ea1ca8dd108d5aad740e9a82099a251c33df4c09ba56039fa438455bf0de

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < 1) || ((minMiddleIndex) > 360)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Chart7
### Patch Diff Hash-SHA-256:

7b99c6eae0cfdae34d2f77efc33301142e7f15f330e35ae76c24e66e4b2c290c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) % 400) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Chart7
### Patch Diff Hash-SHA-256:

d3eb55daa6be461f5882f8f9eb380fa9b8164bf0ddb6661ece4bb4e9710030e0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Chart7
### Patch Diff Hash-SHA-256:

1abd879eebc9a1c8d2970333c54319755032c2542550cfdf6cbe36477e1aeaa6

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (!((0 == (maxMiddleIndex)) && (0 == (minStartIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Chart7
### Patch Diff Hash-SHA-256:

3356647d0e5b659446c9254459abd8fb4ab1c294e7d925fcedc8e1dbed5b7ec0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (org.jfree.data.time.SerialDate.isLeapYear(minMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Chart7
### Patch Diff Hash-SHA-256:

0e1c8cd31716fa7fed6d8de7eed0ad743f665cddaaa56892b309d3f7228009d7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) == (maxMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Chart7
### Patch Diff Hash-SHA-256:

3e291f1276cbc9752c4fee7a52957fbe5c68cae6a2fe37e375559b4d47b78cff

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxStartIndex) == 0) || ((maxMiddleIndex) == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Chart7
### Patch Diff Hash-SHA-256:

b1f38617d6bb3bad4e48cb63ae7bf1b9dc977dae302f42e514f76841be56a0b5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) != 1) || ((maxStartIndex) != 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Chart7
### Patch Diff Hash-SHA-256:

ed939fccd54a05d3c02005b164fdcd3a22d02c8d6d706c529db25cd7fe4a8ee6

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Chart7
### Patch Diff Hash-SHA-256:

6e1fd7ef7175bc8211fa4567f506acfaa9a9ab5c2809b9cc096a7a4998392cdb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) == 0) || ((maxMiddleIndex) == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Chart7
### Patch Diff Hash-SHA-256:

3dc3fd8b85e22596ff1d36df03bd46a6cce8999672f8ddc79c83b39514dc7d36

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) < 1) && ((minEndIndex) < 5)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Chart7
### Patch Diff Hash-SHA-256:

22767b797b677a591a587d9ac662ad505435465a699c8a23f7ea857cbb749027

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) > 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Chart7
### Patch Diff Hash-SHA-256:

c5716766d70b59c35023ce16023c33da88b1cba59541c6290c1477841c55422c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (org.jfree.data.time.SerialDate.isLeapYear(minMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Chart7
### Patch Diff Hash-SHA-256:

48c4122f6339c6d83476904c009a66c4a014055b52c745e6df5b3ceddd0d5618

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) > (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Chart7
### Patch Diff Hash-SHA-256:

68b9d45745677428c06f1fd57c33a1395c158971aab337d8d66482d9a610f392

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) != 2) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Chart7
### Patch Diff Hash-SHA-256:

706722c5901cffd82d2bab3306154f2c35a3e61faaedb6c642d3a3cd5ef43341

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((maxEndIndex) == 0) || ((minMiddleIndex) == 0)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Chart7
### Patch Diff Hash-SHA-256:

fb57ffa0a4c2955d90468712a4b756ff14db43da84cdf9bc7a9b2f3eb2adba69

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) % 100) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Chart7
### Patch Diff Hash-SHA-256:

56f999d6f421ef3c4112be0cd8efbb0f65ff96c48a2e787b4ad84810ae7f7f0f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || (index == 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Chart7
### Patch Diff Hash-SHA-256:

2334200908d7ec7d67e2ee66e3ea45fdf4ba039bf7357de93100fdc1f15050ae

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index < 1) || (((maxMiddleIndex) < 1) && (index < 5))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Chart7
### Patch Diff Hash-SHA-256:

13fc72a5cefa0f7f190b8727ee4cf32d2e0ed4022592127035362d172c9fe5e0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) > ((minMiddleIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Chart7
### Patch Diff Hash-SHA-256:

4184720c8cd64e6800be2dd00092262e5d4964e1610c438e558e42243c36512e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (0 == (maxEndIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Chart7
### Patch Diff Hash-SHA-256:

7f7c1533ae263c46aaeaa666d7d7fab97fd0cc54672c5a8b90d72be4d44e7614

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) < 1) && ((maxMiddleIndex) < 5)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Chart7
### Patch Diff Hash-SHA-256:

c01ef2f11dc973177b97311c80fb0d9838a5a7bf08ff0780fdeb883ed33ba24f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) == (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Chart7
### Patch Diff Hash-SHA-256:

5913157a47e1281c6189e58ef566907f3d230fe057b8ec0fbd68a645d1411247

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Chart7
### Patch Diff Hash-SHA-256:

802f71de21b72efd1be3b8912f3ee73168b79ca831268cf29f971ab0ffa32649

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (0 == (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Chart7
### Patch Diff Hash-SHA-256:

df7cee70ca03c5635ec7a75cc2a7e21060da8f43a1ec9fb0a85d72dbaebc900a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) > (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Chart7
### Patch Diff Hash-SHA-256:

6984ee4f32bec0c0ec97d6dc7e400f557129888730db2e812e3e7af92aa792d0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) != 2) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Chart7
### Patch Diff Hash-SHA-256:

32f05b741f58d009f26b349ce77e6e3f89e85cec9b5eeef57013c79c9d602e0e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minEndIndex) == 0) || ((minEndIndex) == 1)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Chart7
### Patch Diff Hash-SHA-256:

4e06f7408ab810f20d1f4365585cd98abd2c0d62b0b8e43c12ff73fe0b7d6649

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((minStartIndex) == (minStartIndex)) && ((minStartIndex) > 0)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Chart7
### Patch Diff Hash-SHA-256:

96cb2432b7d665be371e3e8d5a879c7dcc79696c9829d0f6d9377d645006bd09

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (0 < (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Chart7
### Patch Diff Hash-SHA-256:

d572b5b9452d53345babfdf8b1c119309f348cbc642a3c7cda5744381e6d80e7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (!(org.jfree.data.time.SerialDate.isValidMonthCode(maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Chart7
### Patch Diff Hash-SHA-256:

3caade467397d4dfc65d884cd85ba986aeb9e54e5b87a4c66290d6d589611a25

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index == (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Chart7
### Patch Diff Hash-SHA-256:

3eb4410ae37d66406c80968679074da5fced5d7f15bd5fed6da3b7d37a9dbf2a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Chart7
### Patch Diff Hash-SHA-256:

8e5f49118b886485b05fbe39630b550fee2deea72ce4389266512cb04b4eff3e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxEndIndex) < 0) || ((maxEndIndex) < (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Chart7
### Patch Diff Hash-SHA-256:

7732d5f7058083afc0240e604d33b099bc050b88565e5805a4b833967112a291

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Chart7
### Patch Diff Hash-SHA-256:

de581a9c2c7b02ee8ae51d9df766c27c49c98f371897204bca44123ad8c36b5d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((maxStartIndex) > (minStartIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Chart7
### Patch Diff Hash-SHA-256:

77e94697a1f38b5aafe6eaf379d540a9087d1332389598e6e1ce51f33ead22a8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) >= (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Chart7
### Patch Diff Hash-SHA-256:

a5e3c2576d8c9f6348666e85d256d24074b9641621e69c4f8a0ad4d375eb783d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) > (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Chart7
### Patch Diff Hash-SHA-256:

031cb8978ad3354c3938a8e5be2e7c5c509a954274d3f5dab1b5ec7966f5e398

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (!((0 == (maxMiddleIndex)) && (0 == (minEndIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Chart7
### Patch Diff Hash-SHA-256:

abf9e4930331a51bce7fb13eae81bc52a5e9e4b07cd5c58cf02f715105c1c472

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) == 0) || ((minMiddleIndex) == 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Chart7
### Patch Diff Hash-SHA-256:

7e4844f42d24b1e5fd15c76a131015608ad8dc239a10654166460c490d50b634

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((maxEndIndex) % 400) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Chart7
### Patch Diff Hash-SHA-256:

d1cf158d5b9faaa05f84bfb9e593e9c159b9312764d141a541f408ac36243a43

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= 1) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Chart7
### Patch Diff Hash-SHA-256:

787d05a9996074d216bb203d6aeb05a2dcf5b3170c59baecf821c5d77d29dd73

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (!(org.jfree.data.time.SerialDate.isValidWeekdayCode(minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Chart7
### Patch Diff Hash-SHA-256:

45c4d3530f6fd1c83102c8ab3bdf0e1ac8f914971a104300e7b06335fac4b96c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) >= 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Chart7
### Patch Diff Hash-SHA-256:

95e87c564c3d7141de8fe5f581a205fd4b1dd9683395190ace8b818159925002

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) != 1) || ((maxMiddleIndex) != 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Chart7
### Patch Diff Hash-SHA-256:

5bd43b5c8472126dfa68285c1b1ed5e39d41127ffdfa1dcf872e1acbd8751419

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (org.jfree.data.time.SerialDate.isLeapYear(maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Chart7
### Patch Diff Hash-SHA-256:

8f7b2d885574e322b324e21cb4780672403f4bea3997b1789723ca63d80ce5cf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Chart7
### Patch Diff Hash-SHA-256:

ee9fa34d40140b27a9f6e09dee6e48abcf792785823fca1652604593dbc1daf3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (org.jfree.data.time.SerialDate.isLeapYear(maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Chart7
### Patch Diff Hash-SHA-256:

d5df2d2bca09c76399996a3c333aa058ce9a81c8e3e5ab54af2468458320a5f1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((minStartIndex) * (maxStartIndex)) > 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Chart7
### Patch Diff Hash-SHA-256:

ae086a9ade8053f8d04714b2fb9a965ecdb27a03c74a6d5d57266b3517ff080a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) == ((maxStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Chart7
### Patch Diff Hash-SHA-256:

0ac7bb1a5fdf368594227c58955c4d15b2850d5d20dee8ff00818e74370dd0dc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) == ((maxStartIndex) - 1)) && ((maxStartIndex) != 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Chart7
### Patch Diff Hash-SHA-256:

a60b562646899df16270796e732a5a76800877409580020a693361046d143348

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (!(org.jfree.data.time.SerialDate.isValidWeekdayCode(maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Chart7
### Patch Diff Hash-SHA-256:

7dfea3e1dbf27f613348c7f5c271adddd66e2c6958fcd5ac297cc5a1582f0354

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((minStartIndex) >= 1) && ((minStartIndex) <= (org.jfree.data.time.SerialDate.lastDayOfMonth(minStartIndex, maxMiddleIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Chart7
### Patch Diff Hash-SHA-256:

ba89bd9b60c884b9c64bdc538f3fe3a954d314180898a824aac33e149eb9f16b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minMiddleIndex) % 400) == 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Chart7
### Patch Diff Hash-SHA-256:

3b8b2d06a9ecc963ba0d5ed27ecf2a3ada1f6cdccdac4d0b58a7752fa6ff6e7b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) < s) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Chart7
### Patch Diff Hash-SHA-256:

9b5f9b9b63c04428c71b46d85e8936698925fea236fcecee4f8899f1f41d200d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) == (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Chart7
### Patch Diff Hash-SHA-256:

ce2532ddfdcec35faf146cff8705f3e644452653d6acaf937dd80fff99591361

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minMiddleIndex) == 0) || ((maxMiddleIndex) == 0)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Chart7
### Patch Diff Hash-SHA-256:

a7248589ec28519e13cbef13be8129a1ed83052e30be9cf0d9e0dc59b656645b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (((maxEndIndex) % 2) == 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Chart7
### Patch Diff Hash-SHA-256:

63a15aecdce9df67bcbdfee6af7a4dfbd4704e87b6a124e0a8f8409723a302c1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || (((minMiddleIndex) > (-4)) && (index < 2))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Chart7
### Patch Diff Hash-SHA-256:

bfd6cc6d57c0295811fc82887f0e5cc478111982841fb91e25205e5fee45c1ce

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) < (4 - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Chart7
### Patch Diff Hash-SHA-256:

eb27fb4fe653df80c578a1fec0c3c3c813251e0136d1189b08eaa09eecd39eca

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) == ((minStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Chart7
### Patch Diff Hash-SHA-256:

1013f598dc0c8242270606c524b606be044873b4bc67928d1a0537faf3635795

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((maxEndIndex) >= (minStartIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Chart7
### Patch Diff Hash-SHA-256:

cd6936979f270e939ab28074d2d7c853cf3a290307de5881c60cb2e9238d8167

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) < 1) || ((minStartIndex) > 12)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Chart7
### Patch Diff Hash-SHA-256:

6542d717441a199406a905fbf08f785f372f6907b6f793e9c32ed1aaeb84d81b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) == 0) || (index == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Chart7
### Patch Diff Hash-SHA-256:

f90165345475b7970e6610f10508ddabb09af5ff67d4e820645f1d9572091d66

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxMiddleIndex) == 0) || (index == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Chart7
### Patch Diff Hash-SHA-256:

531a598016d948b63c00a271b426139bf64fdcf16af88956fdb5bdf1cf0cd58f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((maxEndIndex) < 1) || ((maxEndIndex) > 360)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Chart7
### Patch Diff Hash-SHA-256:

673e04dd868613c3ab166ec111cd0684294ac056dbf3d762dd8990c5dd9369d3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || (((minEndIndex) > (-4)) && (index < 2))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Chart7
### Patch Diff Hash-SHA-256:

aaed0aa939f95b2c347edc8db3724acb934b62104b94d9286455c19eb84a1f83

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (s > 0L) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Chart7
### Patch Diff Hash-SHA-256:

aaa20600d3023f308593bf68c9ce277404708a2a2a7856045c8b4c7f6f7d57fa

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || ((maxMiddleIndex) == 0)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Chart7
### Patch Diff Hash-SHA-256:

6adf6516f9b169f02198b3422ea264900ab48e1fa5a140b5732ac5d68e4aba41

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == ((maxStartIndex) - 1)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Chart7
### Patch Diff Hash-SHA-256:

a0da3486dfbacd6b83caae391a876a9c7d065f707654b037a85fc7536926f8d5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxStartIndex) < s) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Chart7
### Patch Diff Hash-SHA-256:

f6996d4cd7ca86a000edcabeb5504982a92e9677b682c6a92fe7d3d68f55efce

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minEndIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Chart7
### Patch Diff Hash-SHA-256:

a989a7ee1f7e2e0b34d018f3fbc5dd4816f46326cc17a8001023e0aacdc65e50

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((minEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Chart7
### Patch Diff Hash-SHA-256:

a13941439e1c3203a604bd6d26ae29bce610532d5e6f1a12c5ab6b2735713247

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxEndIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Chart7
### Patch Diff Hash-SHA-256:

3e24917266252cbd4b0fffb0d3de1bbfd6323ceba3bf8182189782622ff0e0c3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Chart7
### Patch Diff Hash-SHA-256:

9056b78fde21bbb0050f2ee7a9350e5fcc5c0f8e74947a16de9e41ad3b9cbe4e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= (index - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Chart7
### Patch Diff Hash-SHA-256:

cd30f163acaf881e1f5bb0e7f3150d0613c509053cb1416a55ac07e12e99be88

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((maxEndIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Chart7
### Patch Diff Hash-SHA-256:

3d97f5ef3d98031663a2020ed3c6398cc488a023aeef4e008b28f48b8a5762d4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Chart7
### Patch Diff Hash-SHA-256:

d773a673351ee3f083b8d53788adf4b7fd7c03569d2b21e1d3b12a446ad27268

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= (index - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Chart7
### Patch Diff Hash-SHA-256:

620afa1df9b1240514aedb2bd3c5cfb905c5eeb737ce356487380a7e4c24f9ad

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxMiddleIndex) <= ((minStartIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Chart7
### Patch Diff Hash-SHA-256:

0fae68631ac435db03d12acc7974d516b649773d87e1b0568968cebb4c33d4fc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minStartIndex) - (maxMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Chart7
### Patch Diff Hash-SHA-256:

16b5497ef0334065e91c558efa4c1d74036204bf8c0b876a402f0413575dc367

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Chart7
### Patch Diff Hash-SHA-256:

a163b7801961e93b5fa68c329072b6e76d24b68913cca738aadd1579ef49cb0f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((maxMiddleIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Chart7
### Patch Diff Hash-SHA-256:

e330453d001a905d32957f4f7c02f0e8fb8227a35a606657eebac70f5350cfd0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Chart7
### Patch Diff Hash-SHA-256:

6653869307abb4bc7e14a07b5fe23833797cdac189dd44ca062cc77057dcc5da

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Chart7
### Patch Diff Hash-SHA-256:

18331754ef65eb634c0e6a9088096fbb74b42f39b18dd5ea7accfdc4317e0542

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minEndIndex) <= ((maxMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Chart7
### Patch Diff Hash-SHA-256:

cf28bc5f47c3c107de08df62bd297ba2edd832c71d75e4551779c1b756b551ae

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxEndIndex) <= ((minStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Chart7
### Patch Diff Hash-SHA-256:

98ba488a5302eff55d2a86bfd50bef2178cd1fe8ffceb882c529efdef515947f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((minStartIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Chart7
### Patch Diff Hash-SHA-256:

b19632e41ba2d157aca577a879cede82705296dd5a61af3e0d55420765c4bf9c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= ((minMiddleIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Chart7
### Patch Diff Hash-SHA-256:

6c47633462ee82853e2ed03ccd07abc0cab9d4c90b1c694c9360f4cd2141c5db

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index < (4 - index)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Chart7
### Patch Diff Hash-SHA-256:

64f784d2d2b14e53895569fdbb7ddc6de17ff3e23d8bbf90fc12ff5dd2307cdb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((index != (org.jfree.chart.plot.CompassPlot.NO_LABELS)) && (index != (org.jfree.chart.plot.CompassPlot.VALUE_LABELS))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Chart7
### Patch Diff Hash-SHA-256:

115fafcb57da18e9c2931a66d36a1ad68c8b68c0456e13db259b4c5ad72166e5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index == 0) || ((index > (-4)) && (index < 2))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Chart7
### Patch Diff Hash-SHA-256:

a980282c0887e342d48d6d065d7ab81115893ba3c6a0a6aa8e98d57eb64c82a0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (index == (org.jfree.data.time.SerialDate.INCLUDE_FIRST)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Chart7
### Patch Diff Hash-SHA-256:

2a190b15a727cd2297d455b9ee38452539152c0fe178d7367f34b7afd34c7eae

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index == (org.jfree.data.time.SerialDate.INCLUDE_FIRST)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Chart7
### Patch Diff Hash-SHA-256:

987ff65d8b6ed065d373a6eba30407098f9112a28441a5df111ae23933b244d9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index != (org.jfree.chart.plot.CompassPlot.VALUE_LABELS)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Chart7
### Patch Diff Hash-SHA-256:

d2b4b44985b7f8dd147ba468dd96d60b770fabc9cfa7044154c7a17954beaaa8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index != 1) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Chart7
### Patch Diff Hash-SHA-256:

9e0df15c56caa4b4c806a9950f42d6a19c11dcf37f32180de8f2ef52a9118410

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (index == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.SHAPES)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Chart7
### Patch Diff Hash-SHA-256:

a98e9a191db8af3a50edb779275418bb44c0f05687ca7f40e75dc74834db6972

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((index > (-4)) && (index < 2)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Chart7
### Patch Diff Hash-SHA-256:

ff56a52f0f2ee3fbfb9e7992bd3023a249dfe754d625e37fb9c698e1e06e339d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.SHAPES)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Chart7
### Patch Diff Hash-SHA-256:

88f6a0a09ea6be3373246a77af5285a55db6873a700a664cc9d1a45f0251bedd

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((index & (org.jfree.chart.util.Align.BOTTOM)) == (org.jfree.chart.util.Align.BOTTOM)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Chart7
### Patch Diff Hash-SHA-256:

78ce3d352f24fc21b1e937acd57ad9fac43c3a1ff9add3ee1a19537aa6bc341b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == (javax.swing.JOptionPane.OK_OPTION)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Chart7
### Patch Diff Hash-SHA-256:

437c379a52ca331697340789b208dae1eb2ec856e4238a7c6e7b829a5992c8f7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.SHAPES)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Chart7
### Patch Diff Hash-SHA-256:

dfcb6e6f69bd66e6adb14b719e889e52ca249eab48a57611abaf2001289e5d03

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((index >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) && (index <= (org.jfree.data.time.SerialDate.SERIAL_UPPER_BOUND))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Chart7
### Patch Diff Hash-SHA-256:

f7ed5da72515bef64953ae4cd0624a89596e03973b818993c06e3a7abbc97f7b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) % 400) == 0) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Chart7
### Patch Diff Hash-SHA-256:

8724808fa3a663ffacab0762a9eaf9bf7dc8b9165095269b4e03789cc730c937

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((index < 1) || ((index < 1) && (index < 5))) || (index < (4 - index))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Chart7
### Patch Diff Hash-SHA-256:

ae07103ac343e4aca5735bace9ebf1d4f13ef1df8318b9893f193faf981320a0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (org.jfree.data.time.SerialDate.isLeapYear(minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Chart7
### Patch Diff Hash-SHA-256:

da0ef1458c6287c60a333702e2649427e8400f7aefbdec56c26e03b099d6d5ec

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < (org.jfree.data.time.Week.FIRST_WEEK_IN_YEAR)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Chart7
### Patch Diff Hash-SHA-256:

c4dde14da2e9ed21bd7a69a13b3ccfc0969e92ed2b70a060de9491e06d50003e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.SHAPES)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Chart7
### Patch Diff Hash-SHA-256:

50595f9084e96406ed0eb2cca1d0dd79425ecfdac49e5458809423492457c74e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) == (javax.swing.JFileChooser.APPROVE_OPTION)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Chart7
### Patch Diff Hash-SHA-256:

f6efb54bce24365e921046e26518acbf42d575536cd0dc63a93de75196b0aae7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Chart7
### Patch Diff Hash-SHA-256:

86d14647a4b921aa246fa26d0d15cd2a28a7d436a712afd342ecd267dfc5a677

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (org.jfree.data.time.SerialDate.isValidMonthCode(minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Chart7
### Patch Diff Hash-SHA-256:

c57fdcb2dca69d0c6efc256c352b177a602eb166c258dd06c08a59bc20ae41f1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) == (javax.swing.JOptionPane.OK_OPTION)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Chart7
### Patch Diff Hash-SHA-256:

9a2fce01ddf0e43f21e7f18f7f8cdb244c23cca18421e2b399589497d6967743

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((index != 1) || (index != 1)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Chart7
### Patch Diff Hash-SHA-256:

6d7a0dc9d67a095c28dfa7b1d22d0ad1ff5d54948c6dfcea902a3b038846f7b2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((((minStartIndex) < 1) || (((minStartIndex) < 1) && ((minStartIndex) < 5))) || ((minStartIndex) < (4 - (minStartIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Chart7
### Patch Diff Hash-SHA-256:

28a4255ac2112ded930341f6361964975c43210ee94265af61dc348d91e5024a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.LINES)) != 0) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Chart7
### Patch Diff Hash-SHA-256:

97e48bc5c298f6fe89ab0e8a52664b572c9bf43f867ada096f65ac07d4fb2144

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) < (org.jfree.data.time.Week.FIRST_WEEK_IN_YEAR)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Chart7
### Patch Diff Hash-SHA-256:

d8194b9bd2910b8b0c2cf4cdc679e309c1cf6f6864a231ad8b54fc9ca6433d12

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((0 == (minMiddleIndex)) && (0 == (minMiddleIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Chart7
### Patch Diff Hash-SHA-256:

7122cd118bb082ea9d001121adbbf029e2d624de70959c302fae9cdef558cbc5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) < (org.jfree.data.time.Quarter.FIRST_QUARTER)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Chart7
### Patch Diff Hash-SHA-256:

c17ba1e172330ab506a0c0b9c26d3696e268836d495700c4a7910bf6d6b89a7f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (0 == (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Chart7
### Patch Diff Hash-SHA-256:

ce922c4bd7fb000c05745e7ee288ca6caa3392fda78075b0073185a1340f255d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < (org.jfree.data.time.Quarter.FIRST_QUARTER)) || ((minMiddleIndex) > (org.jfree.data.time.Quarter.LAST_QUARTER))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Chart7
### Patch Diff Hash-SHA-256:

c351993a3f17da021e8cad3609b7c349cf5acddc01543a738af688e849c5db2b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if (((minMiddleIndex) == 0) || ((minMiddleIndex) == 1)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Chart7
### Patch Diff Hash-SHA-256:

eb12d1258debba8de4593bd146cf54ad29a0552578d8ea6e7902390e0b13d117

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) < 1) || ((minMiddleIndex) > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Chart7
### Patch Diff Hash-SHA-256:

16a2bea0087cbb7ae90b2abf52091c40b3f33f5a200038959549c57aa1ed18cf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((index < 1) || (((minMiddleIndex) < 1) && (index < 5))) || (index < (4 - (minMiddleIndex)))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Chart7
### Patch Diff Hash-SHA-256:

8e07db1de5dfc30ad9a48e4e0b4ec64c75ae4784d05c5a1be081d08329c77f28

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minMiddleIndex) == (javax.swing.JOptionPane.OK_OPTION)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Chart7
### Patch Diff Hash-SHA-256:

980b9ea9e1eba9cad8fdb42a92086bf65689c0946fb6727760c872daf9706a97

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minMiddleIndex) == (javax.swing.JFileChooser.APPROVE_OPTION)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Chart7
### Patch Diff Hash-SHA-256:

d39461f79801c42969e826d98c0ce677fe7acd8dbe6c993c7f4ff7dff5a38186

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if (index != (org.jfree.data.time.MonthConstants.JANUARY)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Chart7
### Patch Diff Hash-SHA-256:

cc24dc3337e6a783272d55e9385834629d87091222efd22fcaa62c6c7f98d3d6

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minMiddleIndex) > (-4)) && ((minMiddleIndex) < 2)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Chart7
### Patch Diff Hash-SHA-256:

eeb4dab5ea0a0755f448c103ffcdae1828a7d58f557d872050b82e5e68f964b7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (((minStartIndex) > (-4)) && ((minStartIndex) < 2)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Chart7
### Patch Diff Hash-SHA-256:

704da40941cfc57c4ddaf3b00becac5afb9c8919e125a2d5e10eb24341660a49

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((minStartIndex) != (org.jfree.chart.plot.CompassPlot.NO_LABELS)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Chart7
### Patch Diff Hash-SHA-256:

b0f23f827c99d0d62de3c8b96b3556be97f6e8da9329a7e7f0271a3a6396ba7b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -105,7 +105,7 @@
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxEndIndex).getPeriod().getEnd().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
 			if (middle < minMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Chart7
### Patch Diff Hash-SHA-256:

9fd08c05a78d4c1898a209f9c0375548028480097ad50ba849cfef69b86d0545

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,7 +116,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxStartIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Chart7
### Patch Diff Hash-SHA-256:

dced477420df7c187d000fe99cb337842824adb382fdcb8c22111eb1de5de86f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,7 +116,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxEndIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Chart7
### Patch Diff Hash-SHA-256:

57f30c3a8c5aa65958b6a35c2efd61cf236b005c93517b71124a22b5bd721844

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -115,7 +115,7 @@
 			org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxStartIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Chart7
### Patch Diff Hash-SHA-256:

a845bd6978065dca3619280403f6831355d015f2bfb11e9a394453aa084bfe4c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -105,7 +105,7 @@
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxMiddleIndex).getPeriod().getEnd().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
 			if (middle < minMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Chart7
### Patch Diff Hash-SHA-256:

8dcea85a9b92ded706ae04250ac9f43bcac2c3123d48d91de836ab7d982fe276

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -106,7 +106,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxStartIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
 			if (middle < minMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Chart7
### Patch Diff Hash-SHA-256:

ff8e02ff11869efb04327946a190454fac853d37a56e0b306b6a99c2bc333977

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -106,7 +106,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxEndIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
 			if (middle < minMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Chart7
### Patch Diff Hash-SHA-256:

107123e67707e15bf5a006573e1f026a3e72a4ae3abe324e6252ef9f5478cc74

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -106,7 +106,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
 			if (middle < minMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Chart7
### Patch Diff Hash-SHA-256:

c75d5a5163e1a203e141b058aaee88b1c19584ec335094a94449ddd920e9a57b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -115,7 +115,7 @@
 			org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxEndIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Chart7
### Patch Diff Hash-SHA-256:

59b77ea6ab9feefd3414014152a62331bf29e7a720a1f30978aac8faebd1c806

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,7 +116,7 @@
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
-			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
+			long e = getDataItem(maxMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Chart7
### Patch Diff Hash-SHA-256:

bbbf6143c3af7713979b1fa1bbb58898c50b761edb141bd6879836283fa1c981

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -115,7 +115,7 @@
 			org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Chart7
### Patch Diff Hash-SHA-256:

cf0b5212cd3cf8d4b9c9ed05f2fd321ba0a1d7b6dfe25e745d703098fe602bfb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -115,7 +115,7 @@
 			org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxEndIndex).getPeriod().getEnd().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Chart7
### Patch Diff Hash-SHA-256:

da638becc264152bdb8975e6c78e58c11a1b72d12e2facb97b4be5bc75db8eac

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -115,7 +115,7 @@
 			org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 		}
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
-			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
+			long s = getDataItem(maxMiddleIndex).getPeriod().getEnd().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
 			if (middle > maxMiddle) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Chart7
### Patch Diff Hash-SHA-256:

b2fd1a76b5ae7f7b7c9ab3329f7cfb9d1ce0ff4c6787439527d9f6a47b051c4d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -117,7 +117,7 @@
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
-			long maxMiddle = s + ((e - s) / 2);
+			long maxMiddle = end - s;
 			if (middle > maxMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Chart7
### Patch Diff Hash-SHA-256:

2a947e0750f7bdcce0ae51fcf8c6af2b2b3c8c30f6a7ee168277e8dec32f0b8c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -117,7 +117,7 @@
 		if ((org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex) >= 0) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
-			long maxMiddle = s + ((e - s) / 2);
+			long maxMiddle = middle - s;
 			if (middle > maxMiddle) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Chart7
### Patch Diff Hash-SHA-256:

adfe934a892c1e4d28465baef03105fbc191eec9d8d0f5d7130d2fab38b93968

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if (index <= (index - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Chart7
### Patch Diff Hash-SHA-256:

d8e9ce3d6d19a8bcfb88d184cf36058310247ab56f125bf50248ac7665f6ef96

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= (maxStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Chart7
### Patch Diff Hash-SHA-256:

6f9fd7fda143b298e5a1a005ad7995fee06d833b61d2cd6c4d8ea3876bdb511a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= (minStartIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Chart7
### Patch Diff Hash-SHA-256:

245bef6060dab8d684bab7c3fe106a1ea1118b404783ac14f6d8078d0062dabf

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= (maxEndIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Chart7
### Patch Diff Hash-SHA-256:

fb16b4664468dfe0acf27ce1062fbd2dcaecfe41f4ae3e35db04076819379055

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxStartIndex) <= (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Chart7
### Patch Diff Hash-SHA-256:

ca8ce7b16526d031646d2e7a2419bd5636c4316c5bd0bd5b0d08fd6ed3a528f2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= (maxMiddleIndex)) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Chart7
### Patch Diff Hash-SHA-256:

76b1c5339172f5ebcc4893357e916e893051185f9621cd17199bdb296e37831b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (index - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Chart7
### Patch Diff Hash-SHA-256:

5b8759a3cf65eb2ef7ff0ace40f68677cad2c514e3ab4131f480ad0e740f6733

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minMiddleIndex) <= (maxMiddleIndex)) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Chart7
### Patch Diff Hash-SHA-256:

3218914df8366ed8d4f0eaead4e33218b075cf918b47111cfa98af2b54c821a8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minMiddleIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Chart7
### Patch Diff Hash-SHA-256:

388d68440927e4f29694d2289f359ed7afdf7ae92512029d17a12fc5fd769527

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -104,7 +104,7 @@
 		}else {
 			org.jfree.data.time.TimePeriodValues.this.maxStartIndex = index;
 		}
-		if ((org.jfree.data.time.TimePeriodValues.this.minMiddleIndex) >= 0) {
+		if ((minStartIndex) <= ((minMiddleIndex) - (minStartIndex))) {
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Chart7
### Patch Diff Hash-SHA-256:

2a56a5e6eba51a050a363fa35a57926f43074dc252f5265e2fd3905ff6a76958

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxStartIndex) - (minEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Chart7
### Patch Diff Hash-SHA-256:

09ab90c268f4a62ea994f5e33331f4407b4f013185dc45fcf59afcc2e2520bde

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((minEndIndex) - (minMiddleIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Chart7
### Patch Diff Hash-SHA-256:

848950d1860308ea9ad0fcef16920761581feb65ab674ffed3a6e316ad16fa24

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((minStartIndex) <= ((maxEndIndex) - (maxEndIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Chart7
### Patch Diff Hash-SHA-256:

cd81219c212f51d49717263412d1e9f76b8c3c37d90f0027f7be5c1a94e4e304

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -118,7 +118,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
+			if ((maxEndIndex) <= ((maxMiddleIndex) - (minStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Chart7
### Patch Diff Hash-SHA-256:

bbf62c67e84845e793049f39c66fadad3e1e16dabce05359c3e6c715abcf8e80

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -108,7 +108,7 @@
 			long s = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(org.jfree.data.time.TimePeriodValues.this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
-			if (middle < minMiddle) {
+			if ((maxMiddleIndex) <= ((minStartIndex) - (maxStartIndex))) {
 				org.jfree.data.time.TimePeriodValues.this.minMiddleIndex = index;
 			}
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---