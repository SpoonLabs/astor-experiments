
# Patches of Time11 from Defects4J 
Total patches 10
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