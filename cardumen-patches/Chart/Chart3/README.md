
# Patches of Chart3 from Defects4J 
Total patches 19
## Patch 1 of bug id Chart3
### Patch Diff Hash-SHA-256:

8dada4a8130df5f3481a0aece9c4cea85bbbc6d0b2d5ee474de76a4c5c137437

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = latest <= (maximumItemAge);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart3
### Patch Diff Hash-SHA-256:

06d9bff5822481e10d288f8448c0bdfaa23eccbac596607b04b471b8683db3da

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = ((maxY) / (maxY)) < (minY);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart3
### Patch Diff Hash-SHA-256:

002c6772371179810ef7370beb156fffa3899d3233c8abee111c4fb94b87d195

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (java.lang.Math.cos(java.lang.Math.toRadians(minY))) < 0.0;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart3
### Patch Diff Hash-SHA-256:

1cbcc0541bc7f4978cdd2afc76f2713e4fca295610ead3deb7b4078acccc100b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = !notify;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart3
### Patch Diff Hash-SHA-256:

97293f8bcca250ddb00a5171fb0b7d1e97c5dce52c258c0fe8f4c43c22c5800b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = ((maxY) / (minY)) < (maxY);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart3
### Patch Diff Hash-SHA-256:

8ba6f540796c8bd37b184bb2dcddaf77d6591761be4cdd5a66768d862aaccb15

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = latest < (maximumItemAge);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart3
### Patch Diff Hash-SHA-256:

38a168b0c75f208d779529e65a60cd43c92a65591d4e49990b51c56fb14de043

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (!notify) && (!notify);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart3
### Patch Diff Hash-SHA-256:

6f6406a39d76699e0586e0ea24c6152199cfbfaf8d8f661e92d403b00cab4c08

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = ((maxY) - (minY)) < (minY);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart3
### Patch Diff Hash-SHA-256:

f51eb15dcc10f2c13302d9b457af42d8c1bdfac63743e2abd977d323db87e0e9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = notify == false;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart3
### Patch Diff Hash-SHA-256:

fe8842bb851f59924d662927400ad2b4e83687d5f33673dbea4a8c2c85f4711b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (maximumItemAge) > latest;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart3
### Patch Diff Hash-SHA-256:

989728ad6cf603278646bfe10f3c9a0ea61d5f4799d9ea555e5f4e5e11950fc2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (((maxY) + (minY)) > (maxY)) && (!notify);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart3
### Patch Diff Hash-SHA-256:

7372cabf34870f677d695270d6233dece383d448f2870cfb4bcdd2b40c3a1e1f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (maxY) > 10.0;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart3
### Patch Diff Hash-SHA-256:

1e02d3f6ffade1cb8762ec63c9e2e0acdcc2ffafe1ffbdf27069f652e6974b81

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = ((!notify) && (!notify)) && (!notify);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart3
### Patch Diff Hash-SHA-256:

e6e7aec68112eda113d9a67ae6ed8cb53cba9bbf7032da4ca839851251b29526

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (((minY) + (minY)) > (minY)) && (!notify);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart3
### Patch Diff Hash-SHA-256:

c1f6739c09cc728cca0cfc61e47dc73d5da34f434bc98ad7a339dd097bdaa768

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (((maxY) + (maxY)) > (maxY)) && (!notify);
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart3
### Patch Diff Hash-SHA-256:

973d185312d2835878813e84a4a9d748e9689c8542b1df899a92a406ae71c03f

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -371,7 +371,7 @@
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
-			boolean removed = false;
+			boolean removed = (minY) > 10.0;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
 				org.jfree.data.time.TimeSeries.this.data.remove(0);
 				removed = true;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart3
### Patch Diff Hash-SHA-256:

277a515c59d99ba6a31a7903a61a8c561231e68e908025f08514fe8881a4f9b9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -238,7 +238,7 @@
 			}
 		}
 		if (added) {
-			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (org.jfree.data.time.TimeSeries.this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart3
### Patch Diff Hash-SHA-256:

ec8cd1f9af8ebe36a8509983a9158b5c9a547caaf4c1aaaa8520ec824fa2b938

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -245,7 +245,7 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				findBoundsByIteration();
 			}
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart3
### Patch Diff Hash-SHA-256:

d94600a8fba1c029574d8947a3732857c83f6fa4353e2507efdf58ccdfae7a6e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -245,7 +245,7 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				updateBoundsForRemovedItem(item);
 			}
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---