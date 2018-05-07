
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
## Patch 1 of bug id Time4
### Patch Diff Hash-SHA-256:

44af7f629737761f0c7a5fb00984946fccf7717ff498a41a10ce47fa16a8e172

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return -1;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 2 of bug id Time4
### Patch Diff Hash-SHA-256:

39d14886e62a201127daeea4c0ab4f0c652390cb323081d444b55a7e4235a020

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue();
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

3afc4c551ca48ae568373aba5c4d7e81f3c801adb02492ae83d09804a8e759cc

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

c034e250e18944d0b6ff2af620b6dcfd3024302f975c7a17a9f218a53288b0cd

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue(instant);
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

1cc1190c0cef991831efaee3323146660d25c8c0182b4d58ef420e496bfa6622

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 6 of bug id Time4
### Patch Diff Hash-SHA-256:

8118454a071b78e3f2b1da736e08cbbe7879e3c5cf533ca7091ed0321d509fc6

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

1f5effa5f09d78256465bb9f22243d08f3509daaa56d838d587bc7a8147b0aff

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 2;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 8 of bug id Time4
### Patch Diff Hash-SHA-256:

0263232ac42aa4c7642f7c424581fd02b440285400e80a7d7736f608d4a8e46c

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 9 of bug id Time4
### Patch Diff Hash-SHA-256:

86e1a24b4a2cd3860fc6e29047441ca4698f7d4d6c5534acc1eff2254648c3c9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue(instant);
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 10 of bug id Time4
### Patch Diff Hash-SHA-256:

d07d5698c4833dd44f926199225c756d9e82e5a8d9ba531d3da47ce98aaa0be9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 11 of bug id Time4
### Patch Diff Hash-SHA-256:

7673cd2cebb4752874b8c3602dff03cb05c08c22d05d17988d0e35c7dbda42e4

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue(instant, values)) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 12 of bug id Time4
### Patch Diff Hash-SHA-256:

a8319a39022c41e33c5007ecefeeb781075b4c620b252412fb3adaca304b9bba

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 0;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 13 of bug id Time4
### Patch Diff Hash-SHA-256:

ac1c6f0c7f0cc1052fdbfc61a45da060fe53cf126b20404cf5c3a8fdf9867c8e

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
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

ea84ecde253b80587f1e2d239ce7dfce96398fef1ad0cef5cd15f4b42920ab1a

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 1;
 	}
 
 	public long roundFloor(long instant) {
```


---