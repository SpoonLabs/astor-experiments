
# Patches of Chart3 from Defects4J 
Total patches 18
## Patch 1 of bug id Chart3
### Patch Diff Hash-SHA-256:

a86e529615cf8c94e1911e817b1ab2cc7196c425e0611466d6f582c9a834afe2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,9 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		if (((minY) <= (this.minY)) || ((minY) >= (this.maxY))) {
+			findBoundsByIteration();
+		}
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
```


---
## Patch 2 of bug id Chart3
### Patch Diff Hash-SHA-256:

0a2d0310d361b29c3150210fc622f4f7b8254a19e7bf61408a0a257cb0ed95f1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,7 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		findBoundsByIteration();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
```


---
## Patch 3 of bug id Chart3
### Patch Diff Hash-SHA-256:

63b4f2eb2bb3306b95606e440fd131410f595aec91f661a79f377270647f1a07

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -236,7 +236,7 @@
 			}
 		}
 		if (added) {
-			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```


---
## Patch 4 of bug id Chart3
### Patch Diff Hash-SHA-256:

ac9f236a0384acfd93b4b0ad8e57c6daada95e059b2c38f094a91ee50000052b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,7 +243,7 @@
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
## Patch 5 of bug id Chart3
### Patch Diff Hash-SHA-256:

d3a25005c3783d2d57d8e785452782106ba8b9ce3630a24a04eefcd0dc7f12ea

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -212,6 +212,11 @@
 		int count = getItemCount();
 		if (count == 0) {
 			this.data.add(item);
+			if (!(java.lang.Double.isNaN(maxY))) {
+				if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+					findBoundsByIteration();
+				}
+			}
 			added = true;
 		}else {
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
```


---
## Patch 6 of bug id Chart3
### Patch Diff Hash-SHA-256:

5aa009fd1e53a013c0c4d3ed55580e05250b3e7c7312dc0763787285831cc726

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,7 +243,7 @@
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
## Patch 7 of bug id Chart3
### Patch Diff Hash-SHA-256:

64bae89a6d30b96008bedf888165beb943e5f095e0e37fed98871ac5e45f7ee1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -197,17 +197,16 @@
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
-			if (!(this.timePeriodClass.equals(c))) {
-				java.lang.StringBuffer b = new java.lang.StringBuffer();
-				b.append("You are trying to add data where the time period class ");
-				b.append("is ");
-				b.append(item.getPeriod().getClass().getName());
-				b.append(", but the TimeSeries is expecting an instance of ");
-				b.append(this.timePeriodClass.getName());
-				b.append(".");
-				throw new org.jfree.data.general.SeriesException(b.toString());
+			if (notify) {
+				findBoundsByIteration();
+			}else
+				if ((item.getValue()) != null) {
+					double yy = item.getValue().doubleValue();
+					this.minY = minIgnoreNaN(this.minY, maxY);
+					this.maxY = minIgnoreNaN(this.maxY, maxY);
 			}
 
+
 		boolean added = false;
 		int count = getItemCount();
 		if (count == 0) {
```


---
## Patch 8 of bug id Chart3
### Patch Diff Hash-SHA-256:

91c60d1c6b790d908d55c8075d9b8fef8d7aec5335a2c63558992b658be5ecd1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -189,6 +189,15 @@
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
+		if (notify) {
+			findBoundsByIteration();
+		}else
+			if ((item.getValue()) != null) {
+				double yy = item.getValue().doubleValue();
+				this.minY = minIgnoreNaN(this.minY, maxY);
+				this.maxY = minIgnoreNaN(this.maxY, maxY);
+			}
+
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
```


---
## Patch 9 of bug id Chart3
### Patch Diff Hash-SHA-256:

7637ccb43cd3e140a2d1f26bd9c073da94fb9aef98a565fb42c9fd594128a3c2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -218,6 +218,7 @@
 			if ((item.getPeriod().compareTo(last)) > 0) {
 				this.data.add(item);
 				added = true;
+				org.jfree.data.time.TimeSeriesDataItem oldItem = addOrUpdate(item.getPeriod(), item.getValue());
 			}else {
 				int index = java.util.Collections.binarySearch(this.data, item);
 				if (index < 0) {
```


---
## Patch 10 of bug id Chart3
### Patch Diff Hash-SHA-256:

13a66b047ec2e893ab13a165f47f13b74bfecebdee34e458530f2a5624b78100

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -246,6 +246,9 @@
 				fireSeriesChanged();
 			}
 		}
+		if (((minY) <= (this.minY)) || ((minY) >= (this.maxY))) {
+			findBoundsByIteration();
+		}
 	}
 
 	public void add(org.jfree.data.time.RegularTimePeriod period, double value) {
```


---
## Patch 11 of bug id Chart3
### Patch Diff Hash-SHA-256:

b72440dd82eab7bebe3d8b326bbf6bf30ca9bb895dd5b1a5ab26e222856e88fc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -185,6 +185,7 @@
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
+		updateBoundsForRemovedItem(item);
 		add(item, true);
 	}
```


---
## Patch 12 of bug id Chart3
### Patch Diff Hash-SHA-256:

2b9a1356d856904b5095b59b7438934956b903362f4261bc67f3dfa3e2e236ce

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -193,6 +193,7 @@
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
+		updateBoundsForRemovedItem(item);
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
```


---
## Patch 13 of bug id Chart3
### Patch Diff Hash-SHA-256:

6887fb71803085588a687b9a15191c71588c7a82be7b93b98c21f985603b75a4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -197,15 +197,10 @@
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
-			if (!(this.timePeriodClass.equals(c))) {
-				java.lang.StringBuffer b = new java.lang.StringBuffer();
-				b.append("You are trying to add data where the time period class ");
-				b.append("is ");
-				b.append(item.getPeriod().getClass().getName());
-				b.append(", but the TimeSeries is expecting an instance of ");
-				b.append(this.timePeriodClass.getName());
-				b.append(".");
-				throw new org.jfree.data.general.SeriesException(b.toString());
+			if (!(java.lang.Double.isNaN(maxY))) {
+				if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+					findBoundsByIteration();
+				}
 			}
 
 		boolean added = false;
```


---
## Patch 14 of bug id Chart3
### Patch Diff Hash-SHA-256:

cabd66b8f18c647dfbc54ca128ddf66c847a6019968dd9f179005a9fcc56e2c2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -235,6 +235,7 @@
 				}
 			}
 		}
+		findBoundsByIteration();
 		if (added) {
 			updateBoundsForAddedItem(item);
 			if ((getItemCount()) > (this.maximumItemCount)) {
```


---
## Patch 15 of bug id Chart3
### Patch Diff Hash-SHA-256:

6e8216c69df728743e72cfe8ab3fb78133902682e7cc81ee0c60c521326f4acb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,8 +243,14 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				findBoundsByIteration();
+			}else
+				if ((item.getValue()) != null) {
+					double yy = item.getValue().doubleValue();
+					this.minY = minIgnoreNaN(this.minY, maxY);
+					this.maxY = minIgnoreNaN(this.maxY, maxY);
 			}
+
 		}
 	}
```


---
## Patch 16 of bug id Chart3
### Patch Diff Hash-SHA-256:

ab609fe048b68b79804b97840c9c0ed7e2aafd0d4e9b100532a65e7dacc36755

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -96,6 +96,7 @@
 	}
 
 	public double getMinY() {
+		findBoundsByIteration();
 		return this.minY;
 	}
```


---
## Patch 17 of bug id Chart3
### Patch Diff Hash-SHA-256:

889554ceca93a14420e0c81b7307f3311f5a20334d368d16b4ef5cbc4c1e22e0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -196,7 +196,10 @@
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
-		}else
+		}else {
+			if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+				findBoundsByIteration();
+			}
 			if (!(this.timePeriodClass.equals(c))) {
 				java.lang.StringBuffer b = new java.lang.StringBuffer();
 				b.append("You are trying to add data where the time period class ");
@@ -207,7 +210,7 @@
 				b.append(".");
 				throw new org.jfree.data.general.SeriesException(b.toString());
 			}
-
+		}
 		boolean added = false;
 		int count = getItemCount();
 		if (count == 0) {
```


---
## Patch 18 of bug id Chart3
### Patch Diff Hash-SHA-256:

1cea66c2f6f75d4b7c69ed34a15c4fe36e7c3f123ed3f30a8014561609f88975

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -209,6 +209,12 @@
 			}
 
 		boolean added = false;
+		if (notify) {
+			findBoundsByIteration();
+			if (notify) {
+				fireSeriesChanged();
+			}
+		}
 		int count = getItemCount();
 		if (count == 0) {
 			this.data.add(item);
```


---