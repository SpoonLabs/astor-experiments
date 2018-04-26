
# Patches of Time17 from Defects4J 
Total patches 14
## Patch 1 of bug id Time17
### Patch Diff Hash-SHA-256:

a454f7f4b10ccff4fdc5c5989cc9def4da4dfd84ffab01fe5a53149de3fb7afc

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR));
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Time17
### Patch Diff Hash-SHA-256:

62be5bafaa1a97f33719de2844267e7e07e4bb7eee40bd6a257cea669d229fc1

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instant ^ instant;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Time17
### Patch Diff Hash-SHA-256:

6b8e3c1cd76ac44790bb5ebaac21114e0e089e1a75d1da9ab5754346e4c6cb3e

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instantBefore ^ instantBefore;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Time17
### Patch Diff Hash-SHA-256:

67a3bc604a6b6e70fa905da2b22ec17f045d13d6e61d7a84391bcd0b05037156

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instantBefore ^ instant;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Time17
### Patch Diff Hash-SHA-256:

94198092ffbae0cab3b0ca53c87a19529bb2434217852bf1f451b7cb9b4ff395

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instant - instant;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Time17
### Patch Diff Hash-SHA-256:

9e480b6d12e6b7e9d5ec01cb4ce453f99221d7bbde1af24fe808255124cafdf9

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instantBefore - instantBefore;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Time17
### Patch Diff Hash-SHA-256:

65aea9a6edb9f66be82aa70d1f0ffbaa4570e241cc99dadfea8a9eb38ba055e5

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instant ^ instantBefore;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Time17
### Patch Diff Hash-SHA-256:

863ae7c7492672de9867bf1eb692064200d6698f23eba3387e5bfed855216106

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = nextTransition(instantBefore);
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Time17
### Patch Diff Hash-SHA-256:

36edfb7715aeb903dee1020d365897cde108ede62d70f5f662bc51413a753c79

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = previousTransition(instantBefore);
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Time17
### Patch Diff Hash-SHA-256:

3c1c26b74f292350426107ac4125d395459f1a14b37e3808a138ed6f38b5be29

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instantBefore - instant;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Time17
### Patch Diff Hash-SHA-256:

c17e53a6ac18e8787035895ca1b8ea1c107f1bff5d66401b042898ad2ed4587b

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = instant - instantBefore;
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Time17
### Patch Diff Hash-SHA-256:

14c4f60761ee0728313d322261dd61054c834e814a199034a322077384288a40

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = convertUTCToLocal((instant ^ instant));
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Time17
### Patch Diff Hash-SHA-256:

9c8e186f2dbe04168bf8c5730b59ce14a7cbaac91017c52d630ed93ae94b237a

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = convertUTCToLocal((instant - instant));
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Time17
### Patch Diff Hash-SHA-256:

594b60085fa57802a73084d12e1106c2353dcf0c7cde045deec812780bb00c36

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -550,7 +550,7 @@
 
 	public long adjustOffset(long instant, boolean earlierOrLater) {
 		long instantBefore = convertUTCToLocal((instant - (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
-		long instantAfter = convertUTCToLocal((instant + (3 * (org.joda.time.DateTimeConstants.MILLIS_PER_HOUR))));
+		long instantAfter = convertUTCToLocal((instantBefore - instantBefore));
 		if (instantBefore == instantAfter) {
 			return instant;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---