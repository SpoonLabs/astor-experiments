
# Patches of Time11 from Defects4J 
Total patches 11
## Patch 1 of bug id Time11
### Patch Diff Hash-SHA-256:

aed146d003876be7143397622029627fc2f7d159dc0125f549c6f08ed1825193

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,8 +158,8 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
-					tailZone = rs.buildTailZone(id);
+				if ((org.joda.time.tz.ZoneInfoCompiler.cStartOfYear) == null) {
+					org.joda.time.tz.ZoneInfoCompiler.cStartOfYear = new org.joda.time.tz.ZoneInfoCompiler.DateTimeOfYear();
 				}
 			} 
 			millis = rs.getUpperLimit(saveMillis);
```


---
## Patch 2 of bug id Time11
### Patch Diff Hash-SHA-256:

4d5d52237bd242e2a5ed57e40b72bf2ed6ca135497f22f12f6501412c36c40d4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,12 +746,8 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
-				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
-				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
-					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
-				}
+			if ((org.joda.time.tz.ZoneInfoCompiler.cStartOfYear) == null) {
+				org.joda.time.tz.ZoneInfoCompiler.cStartOfYear = new org.joda.time.tz.ZoneInfoCompiler.DateTimeOfYear();
 			}
 			return null;
 		}
```


---
## Patch 3 of bug id Time11
### Patch Diff Hash-SHA-256:

c99da1ec26c43ee9ed9e917af342d8f90c1ab2c446234ef838461a1da00b4d1c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,16 +984,13 @@
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
## Patch 4 of bug id Time11
### Patch Diff Hash-SHA-256:

5f6feb0ac92a687e28af113898d565806230b8b4039f222b308e1020410d45d9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,18 +983,6 @@
 					
 				}
 			}
-			if (tailZone != null) {
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
-			}
 			return new org.joda.time.tz.DateTimeZoneBuilder.PrecalculatedZone((outputID ? id : ""), trans, wallOffsets, standardOffsets, nameKeys, tailZone);
 		}
```


---
## Patch 5 of bug id Time11
### Patch Diff Hash-SHA-256:

aa519fadbeedaac91648681fdf7424e800e966fc3887c075b8d952cf50a72d04

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,8 +158,8 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
-					tailZone = rs.buildTailZone(id);
+				if (tailZone != null) {
+					return tailZone;
 				}
 			} 
 			millis = rs.getUpperLimit(saveMillis);
```


---
## Patch 6 of bug id Time11
### Patch Diff Hash-SHA-256:

7937b0919add548cd951384771c8564b3d74302d357cb6a0554012dc30a8ee0f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -159,7 +159,6 @@
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
 				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
-					tailZone = rs.buildTailZone(id);
 				}
 			} 
 			millis = rs.getUpperLimit(saveMillis);
```


---
## Patch 7 of bug id Time11
### Patch Diff Hash-SHA-256:

6da0ded5782e2153e5b8a06631e70e93f13939cf88f31a5f74c2113fc2fd5ce4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -750,7 +750,6 @@
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
-					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
 			return null;
```


---
## Patch 8 of bug id Time11
### Patch Diff Hash-SHA-256:

f00b15052162c097549d6314968306420412e165ae4165661096f20567bc3982

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -121,6 +121,12 @@
 			org.joda.time.tz.DateTimeZoneBuilder.Rule rule = new org.joda.time.tz.DateTimeZoneBuilder.Rule(recurrence, fromYear, toYear);
 			getLastRuleSet().addRule(rule);
 		}
+		if (fromYear <= toYear) {
+			org.joda.time.tz.DateTimeZoneBuilder.OfYear ofYear = new org.joda.time.tz.DateTimeZoneBuilder.OfYear(mode, monthOfYear, dayOfMonth, dayOfWeek, advanceDayOfWeek, millisOfDay);
+			org.joda.time.tz.DateTimeZoneBuilder.Recurrence recurrence = new org.joda.time.tz.DateTimeZoneBuilder.Recurrence(ofYear, nameKey, saveMillis);
+			org.joda.time.tz.DateTimeZoneBuilder.Rule rule = new org.joda.time.tz.DateTimeZoneBuilder.Rule(recurrence, fromYear, toYear);
+			getLastRuleSet().addRule(rule);
+		}
 		return org.joda.time.tz.DateTimeZoneBuilder.this;
 	}
```


---
## Patch 9 of bug id Time11
### Patch Diff Hash-SHA-256:

931270367ed67b35ba292148e1b6fe17bbde56c3c896f7a0969f33eeee05ea25

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,17 +983,8 @@
 					
 				}
 			}
-			if (tailZone != null) {
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
+			if (id == null) {
+				return null;
 			}
 			return new org.joda.time.tz.DateTimeZoneBuilder.PrecalculatedZone((outputID ? id : ""), trans, wallOffsets, standardOffsets, nameKeys, tailZone);
 		}
```


---
## Patch 10 of bug id Time11
### Patch Diff Hash-SHA-256:

babb774e8c39bf497f4414c4a6bba4e2ce9477c6ac6c43ba49c7f7c0ddace036

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,16 +984,6 @@
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
## Patch 11 of bug id Time11
### Patch Diff Hash-SHA-256:

432cb94e8142cfbbb211e0dd00aac3d1598ee8df3ae5a8a0b66ffbb95fb87b78

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,9 +158,6 @@
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