
# Patches of Chart3 from Defects4J 
Total patches 14
## Patch 1 of bug id Chart3
### Patch Diff Hash-SHA-256:

836688492bf66f9caa0199e30c9e076d1a037d68466d3570f1f3e83dc5f15e09

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -196,6 +196,7 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		findBoundsByIteration();
 		if ((org.jfree.data.time.TimeSeries.this.timePeriodClass) == null) {
 			org.jfree.data.time.TimeSeries.this.timePeriodClass = c;
 		}else
```


---
## Patch 2 of bug id Chart3
### Patch Diff Hash-SHA-256:

295e07501b1d2f33ce7029a91b150b70a309d9cab4b3b3c168b13ab130b49053

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,7 @@
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
+		findBoundsByIteration();
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((org.jfree.data.time.TimeSeries.this.timePeriodClass) == null) {
```


---
## Patch 3 of bug id Chart3
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


---
## Patch 4 of bug id Chart3
### Patch Diff Hash-SHA-256:

17e5021ca3aa20676cd5a367165aa5ab4794012061c581bbdb2c9d478ff0e608

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -370,6 +370,7 @@
 
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
+			findBoundsByIteration();
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
 			boolean removed = false;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
```


---
## Patch 5 of bug id Chart3
### Patch Diff Hash-SHA-256:

84e620e973f635066e81c1b456a337e87e1001ca7ca996c463f8933917f35b41

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -188,6 +188,7 @@
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
 		add(item, true);
+		findBoundsByIteration();
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
```


---
## Patch 6 of bug id Chart3
### Patch Diff Hash-SHA-256:

6cae1123ff9b333b1516dd18db3572d48bec2af0d7451ce2a99e3778294a9a34

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -188,6 +188,7 @@
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
 		add(item, true);
+		updateBoundsForRemovedItem(item);
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
```


---
## Patch 7 of bug id Chart3
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


---
## Patch 8 of bug id Chart3
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


---
## Patch 9 of bug id Chart3
### Patch Diff Hash-SHA-256:

3af41a93b9fe7f6d81353a7f75e72a7b15ed9effe87622756a3c09cb79a5c790

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -239,6 +239,7 @@
 		}
 		if (added) {
 			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (org.jfree.data.time.TimeSeries.this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```


---
## Patch 10 of bug id Chart3
### Patch Diff Hash-SHA-256:

62d0996007ce43ab8f024735aef5f31501a4f7f30c68d11f17666a079c9f80c3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -219,6 +219,7 @@
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
 			if ((item.getPeriod().compareTo(last)) > 0) {
 				org.jfree.data.time.TimeSeries.this.data.add(item);
+				findBoundsByIteration();
 				added = true;
 			}else {
 				int index = java.util.Collections.binarySearch(org.jfree.data.time.TimeSeries.this.data, item);
```


---
## Patch 11 of bug id Chart3
### Patch Diff Hash-SHA-256:

4eee630b5726a6172f69bd35e2efe1f4e6c6229a361ab566641fd1873cce694a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -247,6 +247,7 @@
 			if (notify) {
 				fireSeriesChanged();
 			}
+			updateBoundsForRemovedItem(item);
 		}
 	}
```


---
## Patch 12 of bug id Chart3
### Patch Diff Hash-SHA-256:

a7f01f4172494551a20e41f62e2dd9dff75a295c4da6f654791fe948469d48d5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -211,6 +211,7 @@
 			}
 		
 		boolean added = false;
+		updateBoundsForRemovedItem(item);
 		int count = getItemCount();
 		if (count == 0) {
 			org.jfree.data.time.TimeSeries.this.data.add(item);
```


---
## Patch 13 of bug id Chart3
### Patch Diff Hash-SHA-256:

43963f639e14be43d3383b95e219a7ed59a27946233c46e8a5b79c4c5d4f9e9c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -214,6 +214,7 @@
 		int count = getItemCount();
 		if (count == 0) {
 			org.jfree.data.time.TimeSeries.this.data.add(item);
+			findBoundsByIteration();
 			added = true;
 		}else {
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
```


---
## Patch 14 of bug id Chart3
### Patch Diff Hash-SHA-256:

6a9e12667eae65a8e1b95b8ceb1b06047deac35c6097eea0d6ee7e7d1a28f5e7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,6 +243,7 @@
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
 			}
+			org.jfree.data.time.TimeSeriesDataItem oldItem = addOrUpdate(item.getPeriod(), item.getValue());
 			removeAgedItems(false);
 			if (notify) {
 				fireSeriesChanged();
```


---