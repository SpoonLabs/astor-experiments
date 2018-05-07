
## Patch 1 of bug id Time11
### Patch Diff Hash-SHA-256:

10de2d446f8fcdedd6cd63f263607cc5a6ec27f98bf70589c832b26a51e30610

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -764,16 +764,13 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
-						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
-					}
+				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey()))
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
 						tailZone = new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(tailZone.getID(), tailZone.iStandardOffset, tailZone.iStartRecurrence.renameAppend("-Summer"), tailZone.iEndRecurrence);
 					}else {
 						tailZone = new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(tailZone.getID(), tailZone.iStandardOffset, tailZone.iStartRecurrence, tailZone.iEndRecurrence.renameAppend("-Summer"));
 					}
-				}
+
 			}
 			return new org.joda.time.tz.DateTimeZoneBuilder.PrecalculatedZone((outputID ? id : ""), trans, wallOffsets, standardOffsets, nameKeys, tailZone);
 		}
```


---
## Patch 2 of bug id Time11
### Patch Diff Hash-SHA-256:

5b6d5aa0e4fbeefdd0df64ad818c3a60c33ee5a56853143ea625f75b841059e3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -764,16 +764,6 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
-						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
-					}
-					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
-						tailZone = new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(tailZone.getID(), tailZone.iStandardOffset, tailZone.iStartRecurrence.renameAppend("-Summer"), tailZone.iEndRecurrence);
-					}else {
-						tailZone = new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(tailZone.getID(), tailZone.iStandardOffset, tailZone.iStartRecurrence, tailZone.iEndRecurrence.renameAppend("-Summer"));
-					}
-				}
 			}
 			return new org.joda.time.tz.DateTimeZoneBuilder.PrecalculatedZone((outputID ? id : ""), trans, wallOffsets, standardOffsets, nameKeys, tailZone);
 		}
```


---
## Patch 3 of bug id Time11
### Patch Diff Hash-SHA-256:

6f65db3f3084729c507f70c340a4f0ed6907dff57642d6bb7402de33413d71aa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -284,7 +284,7 @@
 		}
 
 		public int getToYear() {
-			return iToYear;
+			return iFromYear;
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.OfYear getOfYear() {
```


---
## Patch 4 of bug id Time11
### Patch Diff Hash-SHA-256:

811a7b95132e896226ac5fc7bc5ed18aa471c671b65dd594edf828dac682f663

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -519,8 +519,8 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
-					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
+				if (!(iRules.contains(startRule))) {
+					iRules.add(startRule);
 				}
 			}
 			return null;
```


---
## Patch 5 of bug id Time11
### Patch Diff Hash-SHA-256:

4ede766c6135ab479e3fe6d8b97ca7b3de2a7c587465feef8857d6aaedac2840

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -520,7 +520,6 @@
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
-					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
 			return null;
```


---
## Patch 6 of bug id Time11
### Patch Diff Hash-SHA-256:

aaf43b21343c5bdcea2de014cd69aa6980ad0b6da7f61fbe1aee2284aca4a124

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -1132,9 +1132,6 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
-					tailZone = rs.buildTailZone(id);
-				}
 			} 
 			millis = rs.getUpperLimit(saveMillis);
 		}
```


---
## Patch 7 of bug id Time11
### Patch Diff Hash-SHA-256:

a42a5f1f0df2335d45434631926a25961dd209c91540517b7925ffec777991b4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -519,9 +519,6 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
-					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
-				}
 			}
 			return null;
 		}
```


---
## Patch 8 of bug id Time11
### Patch Diff Hash-SHA-256:

8c6d78637218dbb3763e360e9b7b8219a306ef5b7477c49aa9fd5f61c0c81562

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -375,6 +375,7 @@
 		}
 
 		public boolean isTransitionFrom(org.joda.time.tz.DateTimeZoneBuilder.Transition other) {
+			org.joda.time.tz.ZoneInfoCompiler.cVerbose.set(java.lang.Boolean.FALSE);
 			if (other == null) {
 				return true;
 			}
```


---
## Patch 9 of bug id Time11
### Patch Diff Hash-SHA-256:

a3fda89db66d60eff9da0c85439425d2f045a0ad5d07577d36c28c8a5c0be5f9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -1111,6 +1111,7 @@
 		}
 		java.util.ArrayList<org.joda.time.tz.DateTimeZoneBuilder.Transition> transitions = new java.util.ArrayList<org.joda.time.tz.DateTimeZoneBuilder.Transition>();
 		org.joda.time.tz.DateTimeZoneBuilder.DSTZone tailZone = null;
+		org.joda.time.tz.ZoneInfoCompiler.cVerbose.set(java.lang.Boolean.FALSE);
 		long millis = java.lang.Long.MIN_VALUE;
 		int saveMillis = 0;
 		int ruleSetCount = iRuleSets.size();
```


---
## Patch 10 of bug id Time11
### Patch Diff Hash-SHA-256:

47ee8fc270dbf01c2d7c81438eaa835031eae128a6c0ecdad582a54528406eea

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -1133,7 +1133,7 @@
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
 				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
-					tailZone = rs.buildTailZone(id);
+					saveMillis = saveMillis;
 				}
 			} 
 			millis = rs.getUpperLimit(saveMillis);
```


---
## Patch 1 of bug id Time4
### Patch Diff Hash-SHA-256:

3fc3c311ebadd80e7ab01af4429ab28a0a6128477211feeb7797e611de2397b4

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 2 of bug id Time4
### Patch Diff Hash-SHA-256:

21bf35ce993227aa05dea48bdfb1ee7e33ffb898fcbd1f42f6f38c657bc1e7fd

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue(instant, values)) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

786220cede3c0507e6155256c3e67c36b79124f5fbd8c9595cecc54a8f5b1721

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

89faa0e777d0c0cedc98d099ba74103b487f3e3aba63fdb39fb17f726cde0313

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

5715748db567e37b661ffc3f7550e07b15bc7c4dba763d050ffefc2469e5c5e2

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 2;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 6 of bug id Time4
### Patch Diff Hash-SHA-256:

92aad06ea256c352301c481eba072fd58f0ea635f7970ea7e58ad2d5d69919b5

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue();
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

637620e44e328470d2f96ab3eb9521e5b59019b4f8dc7ce07763315308f4df0d

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 8 of bug id Time4
### Patch Diff Hash-SHA-256:

fb1d15684c0beb8083def465c71b2394c9ddce86b5987628b8e652c0d235b11a

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 3;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 9 of bug id Time4
### Patch Diff Hash-SHA-256:

2c692725f9716e6fdb87822d5b9e11d5d4df2207b1b9b4fedaf6f53b58b305d5

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return -1;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 10 of bug id Time4
### Patch Diff Hash-SHA-256:

b1048b3727500bcb9e49ec2a04eef58b21b9d32c023ceb5fc2763ccd178ac9d3

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 0;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 11 of bug id Time4
### Patch Diff Hash-SHA-256:

fe8ba495982307f425980e138ea7ece582d60b17a14fa8a17885c5a71e10a07e

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue(instant);
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 12 of bug id Time4
### Patch Diff Hash-SHA-256:

27dbb8aed6ef4a3230c02e4361f06b513e78ef2e695181fd1b87b0d0a0b03f71

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 1;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 13 of bug id Time4
### Patch Diff Hash-SHA-256:

70038cdd4dec5984fcbac944bc79c159586c0d8f625528ce3adff1aa5e6c2fd9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 14 of bug id Time4
### Patch Diff Hash-SHA-256:

bf9228bcbe2ab1d66f6b2b44259507504a4b4d3745405757423cfe36bc7a8c98

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 1 of bug id Time20
### Patch Diff Hash-SHA-256:

104e8078c23605c930ba9bc6c689136ffa43b88d3aeb0f0bb381601d33765a13

### Patch Diff:
```
--- /original/org/joda/time/format/DateTimeFormatterBuilder.java	
+++ /fixed/org/joda/time/format/DateTimeFormatterBuilder.java	
@@ -1234,9 +1234,9 @@
 		public int parseInto(org.joda.time.format.DateTimeParserBucket bucket, java.lang.String text, int position) {
 			java.lang.String str = text.substring(position);
 			for (java.lang.String id : org.joda.time.format.DateTimeFormatterBuilder.TimeZoneId.ALL_IDS) {
-				if (str.startsWith(id)) {
-					bucket.setZone(org.joda.time.DateTimeZone.forID(id));
-					return position + (id.length());
+				if (str.startsWith(str)) {
+					bucket.setZone(org.joda.time.DateTimeZone.forID(str));
+					return position + (str.length());
 				}
 			}
 			return ~position;
```


---