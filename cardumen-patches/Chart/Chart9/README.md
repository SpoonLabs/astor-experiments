
# Patches of Chart9 from Defects4J 
Total patches 23
## Patch 1 of bug id Chart9
### Patch Diff Hash-SHA-256:

17fbc32779ae7485a37e03586ba8e9189e455b97fb9783d27b8cd314ac5617d8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if (endIndex < startIndex) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart9
### Patch Diff Hash-SHA-256:

5fde262173192af8150fa76b8146f2dcd0c063048793eb921c8378ec67252e15

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((startIndex > endIndex) && (startIndex <= (maximumItemCount))) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart9
### Patch Diff Hash-SHA-256:

84df1341c63f36d4267fcbe04d7d35f006ac7746b8669e39d74dd4d7894f3bf1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((startIndex > endIndex) && (startIndex <= startIndex)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart9
### Patch Diff Hash-SHA-256:

42b088a8bff4e3362419f88cdb94705025bc0b8b78f6f256747bcb4d278f35cb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if (startIndex > endIndex) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart9
### Patch Diff Hash-SHA-256:

dda8353218a1e3680dd9cfce1e322a902769e31adbd591e919e7e5c9f77dbd46

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((startIndex > endIndex) && (startIndex < (maximumItemCount))) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart9
### Patch Diff Hash-SHA-256:

bcf77031d92ad1f5c08ce0b0468722c43144258a8424d2954e83c7eeb7e8f465

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((endIndex >= endIndex) && (endIndex < startIndex)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart9
### Patch Diff Hash-SHA-256:

686047100938001baa938ef7c77d41d34a06d2cb8c8c1effec4469b0834eda5b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -399,7 +399,7 @@
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
-			if (startIndex == (org.jfree.data.time.TimeSeries.this.data.size())) {
+			if ((startIndex % 2) == 1) {
 				emptyRange = true;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart9
### Patch Diff Hash-SHA-256:

98987b5101c5de2b54ecb67bc909323f988a2acd9df577a566aab66f55887b54

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -399,7 +399,7 @@
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
-			if (startIndex == (org.jfree.data.time.TimeSeries.this.data.size())) {
+			if (((maximumItemCount) * startIndex) > 0) {
 				emptyRange = true;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart9
### Patch Diff Hash-SHA-256:

2ea942afaf29b8b3fa674a8afa9d9f8eb9ecdc2f3f7a5c6dfc615f7dea8ed923

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -411,7 +411,7 @@
 		if (endIndex < 0) {
 			emptyRange = true;
 		}
-		if (emptyRange) {
+		if (endIndex == (startIndex - 1)) {
 			org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
 			copy.data = new java.util.ArrayList();
 			return copy;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart9
### Patch Diff Hash-SHA-256:

0a5f47900c51d56eac0cd97a88e97df913a3d516fa3ebc6a1f36b1fce326b4d8

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -411,7 +411,7 @@
 		if (endIndex < 0) {
 			emptyRange = true;
 		}
-		if (emptyRange) {
+		if (endIndex < startIndex) {
 			org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
 			copy.data = new java.util.ArrayList();
 			return copy;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart9
### Patch Diff Hash-SHA-256:

f54bbd4e996f62fd9f071f231e70c14cd5598041d556a14f67b863b395bc02bc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if (endIndex == (startIndex - 1)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart9
### Patch Diff Hash-SHA-256:

061239c4eda6fb64260a501808321d576e41b68602f1891cef1c80a481344bc1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if (endIndex <= (startIndex - 1)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart9
### Patch Diff Hash-SHA-256:

68a04ae3d550f04f2dc0f9d990da6cfb9984c12adafc314e91233dbca2f160ab

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -395,7 +395,7 @@
 		if ((start.compareTo(end)) > 0) {
 			throw new java.lang.IllegalArgumentException("Requires start on or before end.");
 		}
-		boolean emptyRange = false;
+		boolean emptyRange = end instanceof org.jfree.data.time.Day;
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart9
### Patch Diff Hash-SHA-256:

38be1f1752fc2dc3cbf26aa2c9b61ab9feeb26cad747e200aafd8ce042fa986b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -411,7 +411,7 @@
 		if (endIndex < 0) {
 			emptyRange = true;
 		}
-		if (emptyRange) {
+		if (endIndex <= (startIndex - 1)) {
 			org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
 			copy.data = new java.util.ArrayList();
 			return copy;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart9
### Patch Diff Hash-SHA-256:

f83ccb841e650b611d8976850550f28d38f0c92831f72588dd51e70919e2e945

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -411,7 +411,7 @@
 		if (endIndex < 0) {
 			emptyRange = true;
 		}
-		if (emptyRange) {
+		if (startIndex > endIndex) {
 			org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
 			copy.data = new java.util.ArrayList();
 			return copy;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart9
### Patch Diff Hash-SHA-256:

bf311246b190ba2e6152b097ff1b0424de1d54b53e8d73d23ebdc90f88a99677

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -399,7 +399,7 @@
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
-			if (startIndex == (org.jfree.data.time.TimeSeries.this.data.size())) {
+			if ((startIndex * (maximumItemCount)) > 0) {
 				emptyRange = true;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart9
### Patch Diff Hash-SHA-256:

f4a3e338407df56484efc404e36e96771d318ca89af3d2ffeb81e538fea991d7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((endIndex < (maximumItemCount)) && (endIndex < startIndex)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart9
### Patch Diff Hash-SHA-256:

5805753d554f1535f473c4bba3c606c16baeb9929c2be411111ed9872944fe77

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if ((endIndex < startIndex) && (!emptyRange)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart9
### Patch Diff Hash-SHA-256:

0ff9d2e9a634655173dd081e2e0ab156740233edb8ca806d5113aa8a035f3e1d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -411,7 +411,7 @@
 		if (endIndex < 0) {
 			emptyRange = true;
 		}
-		if (emptyRange) {
+		if ((startIndex > endIndex) && (startIndex < (maximumItemCount))) {
 			org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
 			copy.data = new java.util.ArrayList();
 			return copy;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart9
### Patch Diff Hash-SHA-256:

0aa127a34ca295e8a28fc9f69cec77d1e498ee707d5bbf0cc748124c1dced3b4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -408,7 +408,7 @@
 			endIndex = -(endIndex + 1);
 			endIndex = endIndex - 1;
 		}
-		if (endIndex < 0) {
+		if (emptyRange = endIndex == (startIndex - 1)) {
 			emptyRange = true;
 		}
 		if (emptyRange) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart9
### Patch Diff Hash-SHA-256:

5490bb032bf7722b79d2eb1fe0425fc43e47039e8fdaa6d453baba045ae57597

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -395,7 +395,7 @@
 		if ((start.compareTo(end)) > 0) {
 			throw new java.lang.IllegalArgumentException("Requires start on or before end.");
 		}
-		boolean emptyRange = false;
+		boolean emptyRange = timePeriodClass.equals(org.jfree.data.time.Day.class);
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart9
### Patch Diff Hash-SHA-256:

76cc6621b284a78dcd4bea723ee9d1443c4de3b78d2a97806bc77ebdaace180f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -395,7 +395,7 @@
 		if ((start.compareTo(end)) > 0) {
 			throw new java.lang.IllegalArgumentException("Requires start on or before end.");
 		}
-		boolean emptyRange = false;
+		boolean emptyRange = start instanceof org.jfree.data.time.Day;
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart9
### Patch Diff Hash-SHA-256:

7055cab3832ff3bb694825d8c033926ddcf193836c41501e166599c006ef4184

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -399,7 +399,7 @@
 		int startIndex = getIndex(start);
 		if (startIndex < 0) {
 			startIndex = -(startIndex + 1);
-			if (startIndex == (org.jfree.data.time.TimeSeries.this.data.size())) {
+			if ((startIndex & (org.jfree.chart.util.Align.TOP)) == (org.jfree.chart.util.Align.TOP)) {
 				emptyRange = true;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---