
# Patches of Chart7 from Defects4J 
Total patches 18
## Patch 1 of bug id Chart7
### Patch Diff Hash-SHA-256:

c2a5f319249ac64e04370be9ba9a6e860c19b15731dbb65edfd9f7569d623c42

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -74,6 +74,7 @@
 	}
 
 	public void add(org.jfree.data.time.TimePeriodValue item) {
+		this.minMiddleIndex = maxMiddleIndex;
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null item not allowed.");
 		}
```


---
## Patch 2 of bug id Chart7
### Patch Diff Hash-SHA-256:

9ed1c30226e01cc48b5323a7dbd6c4076f93a052912ae63b139a542ec35da6d1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 3 of bug id Chart7
### Patch Diff Hash-SHA-256:

922e499ec90876da325fff4c8076cae19128a195c8f58a8e36f25d33f38a3c62

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -102,6 +102,12 @@
 		}else {
 			this.maxStartIndex = index;
 		}
+		if ((minMiddleIndex) > 0) {
+			(minMiddleIndex)++;
+			if (((minMiddleIndex) % (minMiddleIndex)) == 0) {
+				fireSeriesChanged();
+			}
+		}
 		if ((this.minMiddleIndex) >= 0) {
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
```


---
## Patch 4 of bug id Chart7
### Patch Diff Hash-SHA-256:

4e6e76902ab0ee7b500b923a0649f7da1c03b0c15cae8cfa3c13bc38dc042109

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return ((maxEndIndex) - (maxStartIndex)) + (maxStartIndex);
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 5 of bug id Chart7
### Patch Diff Hash-SHA-256:

8abd83ba10fbe71b4f063ca6274424ecd6f82dafe4f030d61cc1763731108f81

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 6 of bug id Chart7
### Patch Diff Hash-SHA-256:

2a6f3fa5e0f851de2f747125c121d5789f0dca9032a4f72ae6f7cdc24024b8ba

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return this.maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 7 of bug id Chart7
### Patch Diff Hash-SHA-256:

6edc97935d1b4eb289ec472a2d552df1a0057fecb6d6a1423c2700ffe4f39137

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -155,6 +155,7 @@
 
 	public void add(org.jfree.data.time.TimePeriod period, double value) {
 		org.jfree.data.time.TimePeriodValue item = new org.jfree.data.time.TimePeriodValue(period, value);
+		minMiddleIndex -= maxMiddleIndex;
 		add(item);
 	}
```


---
## Patch 8 of bug id Chart7
### Patch Diff Hash-SHA-256:

b94dfcc8a2e7ed88ba4180e6ccfae321657e9a65600f4139901a3e35d214ac47

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -155,6 +155,7 @@
 
 	public void add(org.jfree.data.time.TimePeriod period, double value) {
 		org.jfree.data.time.TimePeriodValue item = new org.jfree.data.time.TimePeriodValue(period, value);
+		minMiddleIndex = maxEndIndex;
 		add(item);
 	}
```


---
## Patch 9 of bug id Chart7
### Patch Diff Hash-SHA-256:

be1489bf48d15e0527321e8066ac50ec79bdad1e4a97a5a3e29ec0efab31ac53

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,8 +116,8 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
-				this.maxMiddleIndex = index;
+			if (org.jfree.data.time.SerialDate.isLeapYear(minStartIndex)) {
+				maxMiddleIndex = (maxMiddleIndex) + 1;
 			}
 		}else {
 			this.maxMiddleIndex = index;
```


---
## Patch 10 of bug id Chart7
### Patch Diff Hash-SHA-256:

c39454e3e4d3ac821155e912a4ace69801e87a756666b5252507c550b734bc14

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -78,6 +78,7 @@
 			throw new java.lang.IllegalArgumentException("Null item not allowed.");
 		}
 		this.data.add(item);
+		minMiddleIndex = maxMiddleIndex;
 		updateBounds(item.getPeriod(), ((this.data.size()) - 1));
 		fireSeriesChanged();
 	}
```


---
## Patch 11 of bug id Chart7
### Patch Diff Hash-SHA-256:

d9d3f52e3b1e0e3eb61914b9a2e2950c941faecff875bed7fd1cab3f885f60e5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return this.maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 12 of bug id Chart7
### Patch Diff Hash-SHA-256:

e7ce71609ddb26895fd8a4de6ebbc8cc21d95c8ac03c15d5a0be57e795fb095d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -126,6 +126,10 @@
 			long minEnd = getDataItem(this.minEndIndex).getPeriod().getEnd().getTime();
 			if (end < minEnd) {
 				this.minEndIndex = index;
+				if (index >= 0) {
+					this.data.remove(index);
+					fireSeriesChanged();
+				}
 			}
 		}else {
 			this.minEndIndex = index;
```


---
## Patch 13 of bug id Chart7
### Patch Diff Hash-SHA-256:

a9da9e04ea6a2a5f99d61ce70b82f855474ccf0be8779baa9d3a8474bd794604

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -126,6 +126,7 @@
 			long minEnd = getDataItem(this.minEndIndex).getPeriod().getEnd().getTime();
 			if (end < minEnd) {
 				this.minEndIndex = index;
+				this.data.remove(minMiddleIndex);
 			}
 		}else {
 			this.minEndIndex = index;
```


---
## Patch 14 of bug id Chart7
### Patch Diff Hash-SHA-256:

eeced183d6159445d376a03b3df838bee0fbff2e87663cb1d377b75b8025d445

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -96,6 +96,9 @@
 		}
 		if ((this.maxStartIndex) >= 0) {
 			long maxStart = getDataItem(this.maxStartIndex).getPeriod().getStart().getTime();
+			if ((minMiddleIndex) >= (maxMiddleIndex)) {
+				minMiddleIndex -= maxMiddleIndex;
+			}
 			if (start > maxStart) {
 				this.maxStartIndex = index;
 			}
```


---
## Patch 15 of bug id Chart7
### Patch Diff Hash-SHA-256:

cbf48ba363871bd69e6d0bc19662064ba0dba440e7b24f3d5b857be1dda078d2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -127,6 +127,7 @@
 			if (end < minEnd) {
 				this.minEndIndex = index;
 			}
+			maxMiddleIndex = maxStartIndex;
 		}else {
 			this.minEndIndex = index;
 		}
```


---
## Patch 16 of bug id Chart7
### Patch Diff Hash-SHA-256:

cdaaf4b954082818d448b4372abcec8d3c728309409033c62c9e62af06c68588

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -106,6 +106,7 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
+			minMiddleIndex = maxMiddleIndex;
 			if (middle < minMiddle) {
 				this.minMiddleIndex = index;
 			}
```


---
## Patch 17 of bug id Chart7
### Patch Diff Hash-SHA-256:

39100ac10c19d22b16ec1758f34ac43065846e6996127e40daa9335a76f5c666

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,8 +116,8 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
-				this.maxMiddleIndex = index;
+			if (org.jfree.data.time.SerialDate.isLeapYear(maxMiddleIndex)) {
+				maxMiddleIndex = (maxMiddleIndex) + 1;
 			}
 		}else {
 			this.maxMiddleIndex = index;
```


---
## Patch 18 of bug id Chart7
### Patch Diff Hash-SHA-256:

f07c8c242e6a47197832e109b532e97a08f6df006142408aaedabe8539121353

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -96,6 +96,9 @@
 		}
 		if ((this.maxStartIndex) >= 0) {
 			long maxStart = getDataItem(this.maxStartIndex).getPeriod().getStart().getTime();
+			if ((minMiddleIndex) >= (maxStartIndex)) {
+				minMiddleIndex -= maxStartIndex;
+			}
 			if (start > maxStart) {
 				this.maxStartIndex = index;
 			}
```


---