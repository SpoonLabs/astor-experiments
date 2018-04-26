
## Patch 1 of bug id Time11
### Patch Diff Hash-SHA-256:

f1a662461abf4e48283a35f6c1cec2ec80d447392cd4299e899d4a3d17c22a3f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && (millis < millis)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Time11
### Patch Diff Hash-SHA-256:

cdb38ba4c9d5bcb8f3cc3bef43320fcfbdc50131d321d723446504bc710e2339

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("maximum")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Time11
### Patch Diff Hash-SHA-256:

f66ebedce8197186c4d84f579b65661da907dde58e12d78397b337d57bbd6307

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iRules.size()) == 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Time11
### Patch Diff Hash-SHA-256:

fdc459aad17baf2858b2be5ed1aeca703cb0929bacdc02fc597761a8184df60c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if ("??".equals(id)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Time11
### Patch Diff Hash-SHA-256:

4bb7d5247b6d9e1552c9b40951cfe5dc62e1dc5b84ccbb3f1f6040262cf27589

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((YEAR_LIMIT) < (iRules.size())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Time11
### Patch Diff Hash-SHA-256:

6df160db4de6beb12482d860fb0a9aa19bb44c17bd15d3e433421de5ea8be13c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("min")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Time11
### Patch Diff Hash-SHA-256:

9d73fe6d3a39979c6b4b6c1e69d1a6970d6494bd9a9ec9021affd0bd934aabd8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (last.isTransitionFrom(last)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Time11
### Patch Diff Hash-SHA-256:

ad727ab8496ca765a12e40d7f75867e557411421f3d3515b298048c685518f6a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(zoneNameData[4])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Time11
### Patch Diff Hash-SHA-256:

0b1effda34deffdfb6ab753721dfc1afdacfef51dd495595df4d02163525afba

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(id)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Time11
### Patch Diff Hash-SHA-256:

70e9bf4b42881239acb3250f88c50a15d7277c1542e5df1152f569de8e4c2088

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("-")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Time11
### Patch Diff Hash-SHA-256:

1a53143fa88883cef867d8478f5d62bec205908cd6d6953535fa6a45b8577ab5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) == (java.lang.Integer.MIN_VALUE)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Time11
### Patch Diff Hash-SHA-256:

52ee216abbf707b63514c852f6d1d939df5af66c1bfa0d2aba4064cc58c8e3c0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equalsIgnoreCase("Zone")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Time11
### Patch Diff Hash-SHA-256:

0821d9b48b57ad5dc0478427d87f9db5352afaeb4d43abb58f3cfa1ef4908ff1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("UTC".equals(id)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Time11
### Patch Diff Hash-SHA-256:

29dfe5c34862ab8b8d958ef03620894c095276c2e587f256bf497933d1cb7329

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("max")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Time11
### Patch Diff Hash-SHA-256:

a865df8b0a89ba0ee7205133f1235538c2d26369bf62ed3edc8dec1ddcd453e3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("minimum")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Time11
### Patch Diff Hash-SHA-256:

f01150d159ebed7fc43d6d487b25c412df8362878b91c7124c1ef34709af8d11

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.startsWith("last")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Time11
### Patch Diff Hash-SHA-256:

95df2d5398a494918ad2d80f62201137700d14f0f86228b1e6de27d9e1752d00

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("max")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Time11
### Patch Diff Hash-SHA-256:

d06b7d25587243e16ebb8d03398e11a817f9c82715af5f96e56a56525d85ea30

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (tailZone.equals(org.joda.time.DateTimeZone.UTC)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Time11
### Patch Diff Hash-SHA-256:

d4be3fbbd7728f3d0012ba2cabd447a00ed737aee82d340b2e7f6ce0c82fad08

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (transitions.add(last)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Time11
### Patch Diff Hash-SHA-256:

0d7ea172356b144f9379c256eb96888d313079ebb633730dbe3bde7208d93d8e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(zoneNameData[2])) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Time11
### Patch Diff Hash-SHA-256:

04a5c94b7b7c4adc4d2452f6fd9c88aa0204769cd9448b1f4943a054e54485e5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) == (iStandardOffset)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Time11
### Patch Diff Hash-SHA-256:

c2b7baa424ebef97ae34598a86b4368857deceb7c38a95d41fee743924a1a46f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iInitialSaveMillis) > 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Time11
### Patch Diff Hash-SHA-256:

42e6eb895c5e0524e10f931f99fbce05798c258964c0df0dc2d61b5a037a6f9a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size == (java.lang.Integer.MIN_VALUE)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Time11
### Patch Diff Hash-SHA-256:

faccc1052a5a969b2994e07ce93c168dafd9b5db166a870064857807b42fa544

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (endRule == null) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Time11
### Patch Diff Hash-SHA-256:

7246e397aa08fd17f3e2ba80bba43b1669cf222982edbb910dbf2a881a8ccdb6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (org.joda.time.DateTimeZone.UTC.isFixed()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Time11
### Patch Diff Hash-SHA-256:

f73654e6b5ee9656bd1ed3742537090eee5a5e3cf0f624d13273e2115bdd9aed

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("only")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Time11
### Patch Diff Hash-SHA-256:

194ee80a2fdc570ef8dcaa7864d9fc15a8115fcd3d72fa59e2a1c15474580d7f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < 0) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Time11
### Patch Diff Hash-SHA-256:

fcecdc2aa6fa7f97714577805f32fa9d0f5ea3c651b185d242e8af48d15a55e6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < size) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Time11
### Patch Diff Hash-SHA-256:

c214a759cf5cb8e7cd9908c90a3b7b62efa730823a9a2fc057777b119d1546c9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("-dst".equals(zoneNameData[size])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Time11
### Patch Diff Hash-SHA-256:

e9144eb71ec3ad7073a10c4b08a2396071c0df34068639f2e79c98e9d02c3920

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (org.joda.time.tz.ZoneInfoCompiler.test(org.joda.time.DateTimeZone.UTC.getID(), org.joda.time.DateTimeZone.UTC)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Time11
### Patch Diff Hash-SHA-256:

dd105a73e67e406bd74ca27552a7714d08afac097eec6fed7d03157adb06e102

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size == (java.lang.Integer.MAX_VALUE)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Time11
### Patch Diff Hash-SHA-256:

d4982c7a3e48a9003310aaee5b3e6070fc93bcffac9c2283136398a8b90094fe

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (("UTC".equals(id)) && (id.equals(id))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Time11
### Patch Diff Hash-SHA-256:

54a0578e1192bb89ff1d76962f5ebe4f75d809390daab10ba725f04dae6e3021

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (next == null) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Time11
### Patch Diff Hash-SHA-256:

3e3f5b936851367d3d04a24c36a00eca0dacd6bbe179e8ce6ae13d512ddac10e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equalsIgnoreCase("Rule")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Time11
### Patch Diff Hash-SHA-256:

2d9adfd2acaadfd5cfc59dc2199bff2f9caaa361550bdcfec220627dd2a058cf

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (java.lang.Character.isWhitespace(id.charAt(0))) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Time11
### Patch Diff Hash-SHA-256:

534818b03383e78a57684146b8d7220ba05c30bc012bc26c45a9c19a1f5a6947

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size <= 1) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Time11
### Patch Diff Hash-SHA-256:

190294fc91d7e12b97de5ace448fe24d64055e5c28fe26a5597bf912cc9f17c4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("min")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Time11
### Patch Diff Hash-SHA-256:

61a964a57225eacf22970cb46585691dee0f2e963f97b31b96f4a214417aa246

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((transitions.size()) == 1) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Time11
### Patch Diff Hash-SHA-256:

8fab76e72b47502b73dbb1f5c2e7d05c7b8e674af88cf1de8d2f9bcbda461eb8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size == 2) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Time11
### Patch Diff Hash-SHA-256:

b044ea46d738f8f102d5a99834e387949b3d4da19382e47125a1fad429918c25

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (ruleSetCount == 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Time11
### Patch Diff Hash-SHA-256:

ee2df9daef87cc66fbda6ff958a219687bafa5e724859be2923530c4318cb6ac

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size == 0) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Time11
### Patch Diff Hash-SHA-256:

6037c99305068cd77d90ba43306a4c95dbb8f7ee17e25b96ab3af1b8ac1dd43f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((id.length()) == 0) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Time11
### Patch Diff Hash-SHA-256:

24d543f23a19f3f258575ca23e5fe29624de6f5ff35da397d65e60173a75f3f9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equalsIgnoreCase("Link")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Time11
### Patch Diff Hash-SHA-256:

1abc43cb9edf4e666451dc9235794beed26724d040fcf2b3e690a0d8bc34c575

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (tailZone.equals(org.joda.time.DateTimeZone.UTC)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Time11
### Patch Diff Hash-SHA-256:

a4c2fcc7135fa726cfd42626505566fa92ca2f4ff91c29675ccd868d12b2c1a1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((size != size) || (!(id.equals(id)))) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Time11
### Patch Diff Hash-SHA-256:

8a9684c7406749ef0a62f89538bce94c588e664835c56d4b9c08360ab93eaee9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals("24:00")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Time11
### Patch Diff Hash-SHA-256:

1c6c6f9a87fa1316f4029bd19908f7f6b18636fcd3439b9bcd28c47126968edc

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(nameKeys[0])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Time11
### Patch Diff Hash-SHA-256:

4e45a5c85e2af262800fa27c536837615537cce0dc9ae266486bd2bd773bae08

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if ("UTC".equals(id)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Time11
### Patch Diff Hash-SHA-256:

0081253c5017d2b29b7084ace8bde6b81f2f3372f3c31e46bac5517d98128d99

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((transitions.size()) == 2) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Time11
### Patch Diff Hash-SHA-256:

7cce3935b56c9fc60e8b4243e8909bcccc41115a23866cf9b19ce154639b2c99

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < (transitions.size())) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Time11
### Patch Diff Hash-SHA-256:

355fc1faebf20f50ce987384291892ca6c7c73d5846fbee6f37e1a6d5af41a7f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.startsWith("last")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Time11
### Patch Diff Hash-SHA-256:

10c9ac50602be0291faac617dd3ef6038f008f006a78566161dbaf7a338fc592

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -164,7 +164,7 @@
 			} 
 			millis = rs.getUpperLimit(saveMillis);
 		}
-		if ((transitions.size()) == 0) {
+		if (ruleSetCount <= saveMillis) {
 			if (tailZone != null) {
 				return tailZone;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Time11
### Patch Diff Hash-SHA-256:

65a59aa3d5022766b415880678e4346193331ebe84fffb39096fbd18a380a968

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (id == null) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Time11
### Patch Diff Hash-SHA-256:

a4c7b4dfbc336d8ab735b699132b462a00b3a46d1f0587bed5e6d72286f6c83f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < 2) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Time11
### Patch Diff Hash-SHA-256:

ed3fb64274e5e5da7ac2718eba43b899ef920487684b328e603335fbecf79d60

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(zoneNameData[2])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Time11
### Patch Diff Hash-SHA-256:

13889bbc25130f41f1c692c4e3309e8c5100d9948b0cb4cd66b44f4e391a74ba

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (java.lang.Character.isWhitespace(id.charAt(0))) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Time11
### Patch Diff Hash-SHA-256:

499d07130d06f772572b219b5e45fdc0c681e2864b7bf56da42710eb50979a15

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((transitions.size()) == 0) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Time11
### Patch Diff Hash-SHA-256:

4685ef33789495369b6956b5e198fdd50fb61c5874b2c51fbd54dc619b6877c0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("??".equals(id)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Time11
### Patch Diff Hash-SHA-256:

14aa489eaedabd5d9afa315535f2b0179e9cef83c4ed6afd2e36c28562f0a0da

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((iStandardOffset) == (iUpperYear)) && (iInitialNameKey.equals(id))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Time11
### Patch Diff Hash-SHA-256:

4603b8f004d2e8f27916bad505cf03176ef5ccb0efaca112b4758e4ec703b02b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < (iStandardOffset)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Time11
### Patch Diff Hash-SHA-256:

5fb759c14d7e81af9dcd63cbb2f8661cd909b299cbb2e41d7bc0575c3ea02331

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -140,7 +140,7 @@
 		long millis = java.lang.Long.MIN_VALUE;
 		int saveMillis = 0;
 		int ruleSetCount = iRuleSets.size();
-		for (int i = 0; i < ruleSetCount; i++) {
+		for (int i = 0; (--ruleSetCount) >= 0; i++) {
 			org.joda.time.tz.DateTimeZoneBuilder.RuleSet rs = iRuleSets.get(i);
 			org.joda.time.tz.DateTimeZoneBuilder.Transition next = rs.firstTransition(millis);
 			if (next == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Time11
### Patch Diff Hash-SHA-256:

7ac609bbc3b57b600d73f4a521abd15f10b93f0f6fa8a8fabe27e702279b77ae

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((id == null) || (((id.length()) < 3) && (!("??".equals(id))))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Time11
### Patch Diff Hash-SHA-256:

e55f08fdd6a1500a97218cf914b88360f3f4222868cd2b246cccf4fd5efb9080

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.startsWith("-")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Time11
### Patch Diff Hash-SHA-256:

c0b6ba0cf76e5cb8a0a37dda36c39d990de61c680ebb54a63d4875358c130cd6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((id.length()) < 3) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Time11
### Patch Diff Hash-SHA-256:

c601a558db8a389c0f9be1d432215984dc398b08840285d775611a26a52067de

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equalsIgnoreCase("Link")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Time11
### Patch Diff Hash-SHA-256:

c7354a4b5ab1fd2c7658bea24939008363220b7031c3db1db0235bc3dfdb5857

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((transitions.size()) == 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Time11
### Patch Diff Hash-SHA-256:

6491e5b30809f87b2f1c070bbc1dfa922eb96d95fb36d1998c1e45a74243ed78

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < (YEAR_LIMIT)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Time11
### Patch Diff Hash-SHA-256:

d9ff737f378179bdaac0a84a37bbeedfa28362af0abf888accf952efa0c95c95

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (last.isTransitionFrom(last)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Time11
### Patch Diff Hash-SHA-256:

f8aa0e32df7247b5f5138e1edf78c1c1e7479cfff7bdad9bae12f6b971a392e1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) < (id.length())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Time11
### Patch Diff Hash-SHA-256:

276cfea070c7fa093c8d6e0bbaff596d7fca1e9306b7f4f3d2a229da168e216b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(tailZone)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Time11
### Patch Diff Hash-SHA-256:

36ab35f1e668db53a57daa1427df900684a04a5aff353138018f2ea464dadd3d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(nameKeys[2])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Time11
### Patch Diff Hash-SHA-256:

5c01897e9c8f81f4d13307cbc26760fd183177eca243ada5d918828601f3128f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.endsWith("/")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Time11
### Patch Diff Hash-SHA-256:

f46528cdcd093c379f46b7eeb63402c6cd9483bfb94a5f0ff633a44371908083

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (millis < millis) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Time11
### Patch Diff Hash-SHA-256:

29c0850594d946d09a9546db9e4bda626f221ffefeb51300ff50ee63b0977b5f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.charAt(0)) == '-') {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Time11
### Patch Diff Hash-SHA-256:

14fc1b56f0c1deca1b59fc211eefb0e0548ab42cbbac79df13627ed2b8c2c0fa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (id.endsWith("/")) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Time11
### Patch Diff Hash-SHA-256:

070946e0ee72a8683c10bb2bf061bdf60067d82e5d6b5a6c2a4e8abd69c2a11f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if (((iInitialSaveMillis) + 1) < (iStandardOffset)) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Time11
### Patch Diff Hash-SHA-256:

e45ae3a4e7b9cf2f5818bd4974a5e292a81356e2541c624aaa3c3267f80979a1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) <= 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Time11
### Patch Diff Hash-SHA-256:

aa1c02307e056f0f31d9b7ccdc41661c7231af2f14d821006376b7fff9e2fee6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("maximum")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Time11
### Patch Diff Hash-SHA-256:

61c7cd8efb6ade30031f658b23c338143efc1661ec0d7609a1ca0ee68a475ce8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((iUpperYear) < (YEAR_LIMIT)) && ((--(iStandardOffset)) >= 0)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Time11
### Patch Diff Hash-SHA-256:

822bd41a83ea746658778984d6618bac4dc63a0239d9691b3b5caf30a632b15a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (false) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Time11
### Patch Diff Hash-SHA-256:

c92150c2ac6d970e7a6e6aba3f67c058eff821ef05aa19f7fb9adb5e3423d73f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iInitialSaveMillis) < (iStandardOffset)) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Time11
### Patch Diff Hash-SHA-256:

8a5b2cbd8633cd962a7cd80f15c2170958d997592f2d32b60b9c4757ee1f6eab

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((YEAR_LIMIT) <= 1) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Time11
### Patch Diff Hash-SHA-256:

e85565940239ac37e2f1ef07cb22f0fedac504ad4cefe678267b102d26b85a74

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (transitions instanceof org.joda.time.format.DateTimePrinter) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Time11
### Patch Diff Hash-SHA-256:

af3e888772a8be6ce0d52a79b4dae0e74dbd939004b66bcb30496394daf7d5f3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((YEAR_LIMIT) == ((iStandardOffset) - 1)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Time11
### Patch Diff Hash-SHA-256:

5af4e1e499606e27bf90593ae4de4479b78573bda53cd85033e8c7b23a55d11a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.equals("minimum")) || (id.equals("min"))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Time11
### Patch Diff Hash-SHA-256:

88c6f7228f0eb58a43bc22f686945e2f16c3b2f66425183748e05d63f689fe0b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (java.lang.Character.isWhitespace(id.charAt(0))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Time11
### Patch Diff Hash-SHA-256:

777c271e1ac65fea414b05d3fa085c902d938aa67b99f294b6b85b08ec3adb2d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.startsWith("-")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Time11
### Patch Diff Hash-SHA-256:

0a123de29cef09062df1f0dca630961f42d8b51234ca1898cd26f18859c45a19

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == 12) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Time11
### Patch Diff Hash-SHA-256:

afb5acae3c43a1d5bfd6531055c15b7c1441973dc50033de6c535951f3c53c38

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size > 19) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Time11
### Patch Diff Hash-SHA-256:

00807860834e9f1538bea016d82317d75d31305cf22c29ca903799dcd85e5a9f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) > 59) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Time11
### Patch Diff Hash-SHA-256:

236f10dbbb1a9db502f93b0ddcc08a1a8a32b289623d9306f5a807edad25392d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("24:00")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Time11
### Patch Diff Hash-SHA-256:

cd4d0cbf6fc2ade23164c14ceca9f78eeced6c894ef84523476691b81abadfcc

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (super.equals(iRules)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Time11
### Patch Diff Hash-SHA-256:

c6dacc80eb3ba3148db97dd6cc7b0fb9da2a80f802733e24c0684b58eba1435a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (iRules.remove(org.joda.time.DurationFieldType.days())) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Time11
### Patch Diff Hash-SHA-256:

2cebca6a1c3b8340ea51aac42815c982eeb36c3fd19f309db5530f448f15ef18

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (id == null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Time11
### Patch Diff Hash-SHA-256:

b8123979fe902a7aa8aa05204039b4500ca303a709480084368aa1ce612053c8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((id.charAt(0)) == '#') {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Time11
### Patch Diff Hash-SHA-256:

6eed1f588957ef5180b331617dbf542a6f22929fac196553b2375a987b6fd8fe

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.charAt(iInitialSaveMillis)) == '.') {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Time11
### Patch Diff Hash-SHA-256:

3cf372f1cfdb0c6cc6ca427c56707e409ba275e4c0f7f59c0e906bad06d598e4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equalsIgnoreCase("Rule")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Time11
### Patch Diff Hash-SHA-256:

a5bbac88b084108a20e352abe2cf8a1eab068d6e2e2e1102f2cea1fbd7127a73

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (org.joda.time.tz.ZoneInfoCompiler.test(tailZone.getID(), tailZone)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Time11
### Patch Diff Hash-SHA-256:

7fa47d2a3d414f9ae91a71cf29e15360012f3eabee29477c30c83a6fe110f1d8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(org.joda.time.DateTimeZone.UTC.getID())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Time11
### Patch Diff Hash-SHA-256:

0da803e5f26a723041c539ebd583cad2af67a8c13c25a8725f4face8da63b4cc

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((iStandardOffset) == 0) && ((iInitialNameKey.charAt(0)) == '-')) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Time11
### Patch Diff Hash-SHA-256:

52caa54c48678314fe19df484fa5ff04b726d6d0af969f74ddb365a5fbab10b0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) < (121 * 84375)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Time11
### Patch Diff Hash-SHA-256:

0168d2f4a730516c4158604bb94502a78980fbca755c02bd2355f71cf5903bf8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equalsIgnoreCase("Zone")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Time11
### Patch Diff Hash-SHA-256:

2ddf4edc4c3ec06975426a385dac3853fcad2d2589c8031211da51f73fc55963

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ("UTC".equalsIgnoreCase(iInitialNameKey)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Time11
### Patch Diff Hash-SHA-256:

b50908d7b1aa037feac1100476c636a161d993041facde8baf1ffba303d6dd84

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(nameKeys[2])) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Time11
### Patch Diff Hash-SHA-256:

56cd791395a28dadee8fdc94eb93e0889f6eb2a4a0542603886d8fdd24a08769

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (ruleSetCount <= 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Time11
### Patch Diff Hash-SHA-256:

30adbedc5db7b4dcd54758445935211383b7346e8a025e4e8a9e8cbceb362661

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (id.endsWith("/")) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Time11
### Patch Diff Hash-SHA-256:

d123c7f563879aa0bdd2f098caf6809d3759e6fee5aaf5e2aedfae02640fe930

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.startsWith("+")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Time11
### Patch Diff Hash-SHA-256:

6d1fdb56542debc828d2f44b1c771abfbc54390e023b8c073bbcf251d939ebdf

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(zoneNameData[0])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Time11
### Patch Diff Hash-SHA-256:

6d5ef2434c5c174751af341f0011dcc52d0064cf07d2cfa38842c129170a220c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.charAt(0)) == '#') {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Time11
### Patch Diff Hash-SHA-256:

a2a18c01c62262a88c431aaff6f153a4ca9276613d0eda15aaa862e3c8c0c688

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("-")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Time11
### Patch Diff Hash-SHA-256:

b72ad48842c7f6da0d0e36d68617a8cfa450fc43476c2772a2a1a89469ed537f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < (274 * 84375)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Time11
### Patch Diff Hash-SHA-256:

47555c0b81fdd2fdc44094620ae008cd89dbca53b021870ca09ee32c211e32aa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (id.equals("-")) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Time11
### Patch Diff Hash-SHA-256:

c470e11c72cd2ec7f187d9052f9eec44e8967ae73c89724f7c7561e3ed608fb5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((millis ^ millis) < 0) && ((millis ^ millis) < 0)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Time11
### Patch Diff Hash-SHA-256:

8efaed5124ea677fb7d788b3fe31c5aa13211281d04f52e37f9d904d9edd2f7a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (iRules.remove(org.joda.time.DurationFieldType.days())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Time11
### Patch Diff Hash-SHA-256:

6530c3817e768f7199527b1a6cd25d03e23ea559e6cbea3ae920c70271dbe676

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.endsWith("/")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Time11
### Patch Diff Hash-SHA-256:

5b4d610eb32e8c8542c88fc43ce4c49703f203ab68cf694893c2da2f3ee31587

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((size > 28) || (size < 1)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Time11
### Patch Diff Hash-SHA-256:

19bee47bd7214b937389cc3208e1c938765a422b4a46907142cad3e2d4f3480c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("minimum")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Time11
### Patch Diff Hash-SHA-256:

6624bb02b1373bed62cc7d00560462215fd82ffcf3a7209289aa95fd68c02313

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis < saveMillis) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Time11
### Patch Diff Hash-SHA-256:

504604dfa70cf58070bac448df907e6249cdc6d6e28e7e9c961f0e42e83ed71f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iRules.size()) == 0) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Time11
### Patch Diff Hash-SHA-256:

32cc729aeb803644596fae0386ce60ddd2c07df55cfb6aaa7337b22a02f7fc95

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if ("UTC".equalsIgnoreCase(id)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Time11
### Patch Diff Hash-SHA-256:

18c4876ab22915ab3a77462112cca1b18af501b312ab77b6ae90bfe5b494b953

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(org.joda.time.DateTimeZone.UTC.getID())) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Time11
### Patch Diff Hash-SHA-256:

f4f0c5db9d64b5be6e3614bb0a7429ddb54a7d85068edc59c752fa84a2ae2ebb

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(transitions)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Time11
### Patch Diff Hash-SHA-256:

7689711e0d267fec4f5e39f6281a0d48ad5713edad21095e7a60e82633f39a8b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("UTC".equalsIgnoreCase(id)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Time11
### Patch Diff Hash-SHA-256:

2972caf916ddecb2c9d400696bae32f1f04ca0edfddda59c4f56573a99187e5e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(org.joda.time.DateTimeZone.UTC)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Time11
### Patch Diff Hash-SHA-256:

ac7b9c06bb6f976204888c91fb8fec98e661a2cb1d949c75c4000c4937937ddc

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (id.regionMatches(true, iStandardOffset, id, 0, id.length())) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Time11
### Patch Diff Hash-SHA-256:

2c072418467040eea5a86a39eb62b6a236c333cafb0aacf3d644d6bead658d36

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (id.equals("UTC")) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Time11
### Patch Diff Hash-SHA-256:

5a794a51a45c95673bebee7148cfa1c595e3080db246b91b22284f50a901f5d1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (id == null) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Time11
### Patch Diff Hash-SHA-256:

e381a84fc25b7064fd5eb7d3e56162ee05bbc5a5e219c6cbd4c707bdf9ddfc43

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (false) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Time11
### Patch Diff Hash-SHA-256:

9a0513a161dfee8420b5ca510d6865d70dd766eda1aa3ac126ab7e81eee85967

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) == 0) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Time11
### Patch Diff Hash-SHA-256:

1968da62f675daec1d751c0dd6b95e6b8845459bda1249958121473ee3cfae56

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iInitialSaveMillis) >= 4) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Time11
### Patch Diff Hash-SHA-256:

862467de9366492c12889fa9c080ace69c7f0bd2e6502172661f836f3e2a6506

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == ruleSetCount) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Time11
### Patch Diff Hash-SHA-256:

45c91a9ab2e085532590ed0b666208c7a29284da3262804fb4f455d60c4c6515

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (transitions.remove(org.joda.time.DurationFieldType.millis())) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Time11
### Patch Diff Hash-SHA-256:

75ca8403b065e23da6e88c27ca8712b8c6029d2f9d1d31ac85e5c8fb03ca286b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((millis == 0) || (ruleSetCount == 0)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Time11
### Patch Diff Hash-SHA-256:

55e05807b4508e8f859c23ba7a6b75f2c997f25711fa15f3d8cbe4c662715344

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (id.startsWith("GMT+")) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Time11
### Patch Diff Hash-SHA-256:

b69343f5f2e4d741790b221b60913667a41d3bd44132fe171c8453a3514a4be5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.startsWith("+")) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Time11
### Patch Diff Hash-SHA-256:

12ea659673e916bfc2a27f409960c81e2c9a1364a0e230f1d50e0d92e93bb31c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (last == null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Time11
### Patch Diff Hash-SHA-256:

1bf1d7860631ec4ea798e4a915d3efe9991d7d75a2e7e0cad0739cb4d9fbf50e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("-verbose".equals(zoneNameData[size])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Time11
### Patch Diff Hash-SHA-256:

10fcedb0ed824ba1c424d5ae6c4be82a5f798f51921f249b8864332b55884834

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals("only")) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Time11
### Patch Diff Hash-SHA-256:

520d2429b3a5e9ee97ada04bddc118b673e930b3df1d835961ef78404b130507

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < (90 * 84375)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Time11
### Patch Diff Hash-SHA-256:

885c1f47fabd9100dda689e40dffef0d4e0dc5626f460bef168c94c217cd1a7d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size != size) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Time11
### Patch Diff Hash-SHA-256:

79a634cac9bc87ba6ab98b256d3c02093574ae2e86a523090f1a0d8c97586ee7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size > size) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Time11
### Patch Diff Hash-SHA-256:

0fa262e3c3c575d70e2eecb571b4ba93c37418e5905059c8bda091f6b33eda34

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iStandardOffset) == 1) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Time11
### Patch Diff Hash-SHA-256:

fa61a26a80d0da7772842fae8a3d5a31e20371294a2c4772d066cf1a0eced009

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iRules.remove(org.joda.time.DateTimeFieldType.dayOfMonth())) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Time11
### Patch Diff Hash-SHA-256:

0cc8a664774466f5078546b60887f3e26baec29894669d1a5b9d663f0a40de04

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((saveMillis < 0) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Time11
### Patch Diff Hash-SHA-256:

36a2ba85ff82b9050bbd7c856620f9d0103fc505afc3f9cd16c69d5853f51461

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((!outputID) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Time11
### Patch Diff Hash-SHA-256:

4c00d009bccb23d14999e474be90b0df427a86cc8a3c7c26a274ee1179ec0f34

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && (ruleSetCount >= (id.length()))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Time11
### Patch Diff Hash-SHA-256:

c081259622545cea19150ba8c8eef1ce76c3d9f0beff12b25021d8f9b512872b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iInitialSaveMillis) > 1) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Time11
### Patch Diff Hash-SHA-256:

8452b5f8f34ac462e30741237481f8cca8becf19d4e30ddf58646baf6502a608

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("-src".equals(zoneNameData[size])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Time11
### Patch Diff Hash-SHA-256:

d56446a3c96f3851c14fa85ee495018a7b2a5c7a3f1764ba6118526db29fee11

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((id.equalsIgnoreCase("Rule")) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Time11
### Patch Diff Hash-SHA-256:

88cf568fa47066f20b4dc88b64c11f4c7c04f3640a38ccaeef292ca343f9b31f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) < (31 * 84375)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Time11
### Patch Diff Hash-SHA-256:

b5a76fbef9628a8e252cbb8a934244fd87eddc7ef6c0c96a23ccdb700e525446

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < 0) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Time11
### Patch Diff Hash-SHA-256:

6ac58588cb0c6a414ce60635e325c1f957ef44aa15be667c4d68c6c4d15d09d6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -164,7 +164,7 @@
 			} 
 			millis = rs.getUpperLimit(saveMillis);
 		}
-		if ((transitions.size()) == 0) {
+		if (saveMillis != 0) {
 			if (tailZone != null) {
 				return tailZone;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Time11
### Patch Diff Hash-SHA-256:

f3c3e4ffef9c700caf9033d8260f54507a09dd141a6e28985560295c568ab005

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (false) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Time11
### Patch Diff Hash-SHA-256:

81b928a47b8e545fe36fd81e5878d4b2b9a02079ba7dc8bbe2ea5fcab04c4953

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((id.length()) == 0) || ((id.charAt(0)) == '#')) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Time11
### Patch Diff Hash-SHA-256:

b44e8fdaee551b874eb395572bf81bdd39eef2b64c53c633cb88f4fe8c3d557c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((YEAR_LIMIT) == 0) && ((YEAR_LIMIT) == 0)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Time11
### Patch Diff Hash-SHA-256:

4278d0042023421bb0e8dbfa0d92627425524b4f7f8a6c75b85d2fed4daac12c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((YEAR_LIMIT) >= 4) && (((id.charAt(0)) == 'P') || ((id.charAt(0)) == 'p'))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Time11
### Patch Diff Hash-SHA-256:

5d227cc513d97e76eef35cce10a4798d7ea84eb4142bac04135562e705e388eb

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(last)) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Time11
### Patch Diff Hash-SHA-256:

5aea7fe731ed7b678cf2f3a87386520a11118bc88c9b6df556454a44f3e0c8aa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (id.startsWith("last")) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Time11
### Patch Diff Hash-SHA-256:

9c7fd5b085fa989c0098fa700d3502c055094e9a91b8aa32a2e7db1d90f3aafa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && (saveMillis == 12)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Time11
### Patch Diff Hash-SHA-256:

e53d9e03af30c9d8b21c28e742a15e0b83fd4ba51d810bf5a6c1a9e3595bf744

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((id.startsWith("-")) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Time11
### Patch Diff Hash-SHA-256:

376a6cccb7bcf163e4e4b2b138ffcc8c35032df0f64086b3c76586c5ccca46ca

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (id.regionMatches(true, YEAR_LIMIT, id, 0, iInitialSaveMillis)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Time11
### Patch Diff Hash-SHA-256:

c984c4c476819dcbbee677d251e35cf7e6bad9b49e4979aed23124743a92d636

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(last)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Time11
### Patch Diff Hash-SHA-256:

677d597dc2a40840fd77e60edbb2c0f3769ca7e8fddbdafb0eecccead917e2cd

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iRules) == null) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Time11
### Patch Diff Hash-SHA-256:

48ea01e8f5ea266eb933989ec8d316e9c2bf0b115c468ae1f955893ea7dfaac7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -170,7 +170,7 @@
 			}
 			return org.joda.time.tz.DateTimeZoneBuilder.buildFixedZone(id, "UTC", 0, 0);
 		}
-		if (((transitions.size()) == 1) && (tailZone == null)) {
+		if (ruleSetCount < 2) {
 			org.joda.time.tz.DateTimeZoneBuilder.Transition tr = transitions.get(0);
 			return org.joda.time.tz.DateTimeZoneBuilder.buildFixedZone(id, tr.getNameKey(), tr.getWallOffset(), tr.getStandardOffset());
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Time11
### Patch Diff Hash-SHA-256:

94f5e3148036c841c9992c7f0bb4cdc57aef7b60fc94504516aca9240970a9d7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((--(iInitialSaveMillis)) >= 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Time11
### Patch Diff Hash-SHA-256:

953809ed4379f135c7cf8a1caada5ae50277122c13295320c07403050def29b4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((org.joda.time.DateTimeZone.UTC) == null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Time11
### Patch Diff Hash-SHA-256:

0178a380770674d804141dc4eb343aa870c7d3cf13c7b1ddd8df78323b8785fa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if ("-?".equals(zoneNameData[size])) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Time11
### Patch Diff Hash-SHA-256:

995b0bfe8418dd63b1cb415f4f15b963447a3839c52df2576e6be173d90347ff

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((millis != millis) && (millis == millis)) && (id.equals(id))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Time11
### Patch Diff Hash-SHA-256:

5a37d7d97062eb4add413384537b57775d2319cb71019973081724f1e19b74bb

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) == ((iStandardOffset) + 1)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Time11
### Patch Diff Hash-SHA-256:

18bf6670cbd3f2f448c64cdd6aa0be7698a9cbe944ea73bfc38b9095267056cf

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((iRuleSets.size()) <= 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Time11
### Patch Diff Hash-SHA-256:

4fdf15e794822d3299fd976b2baad2c8dd336a3616229fbb074f02bd308f22bf

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < (size - 1)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Time11
### Patch Diff Hash-SHA-256:

d70015c165b2eeabb55f0869346e315cfb53ceb8449f7c4984019a51f483c636

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((YEAR_LIMIT) < 256) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Time11
### Patch Diff Hash-SHA-256:

8872a7741fa7428a4c2b6e5d63f7eee0c5a491a5fe90af005309a3db480daca9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((transitions.size()) <= 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Time11
### Patch Diff Hash-SHA-256:

fcfbbd130c0d7fed91dc17b6defdef32cf75f62db293a2b1579a87eecb2acb4b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) < ((iInitialSaveMillis) - 1)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Time11
### Patch Diff Hash-SHA-256:

083908886172035e39e664fe2f8e934fcc60bc7c1fcefbf8463f11578f01e95e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (tailZone.equals(tailZone)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Time11
### Patch Diff Hash-SHA-256:

afb4984e3e0ce6161463a265302eed90837c24d042f2071e7bcab965496d6572

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((size < 0) || (size <= 0)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Time11
### Patch Diff Hash-SHA-256:

60626c8bbef0dcca9aa4613b29f6d43a75a92280b57b5445b57710f2e059e032

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.charAt(1)) == 'T') {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Time11
### Patch Diff Hash-SHA-256:

77b6801f677e2167e83bd004729e147bdb71a134fa4cfaf821ba05cdd6e4ab0b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && (ruleSetCount == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Time11
### Patch Diff Hash-SHA-256:

02ded8dcb4dc38bce2885caeb1b208e72f2dbf2e665f433d82e9f13715063cee

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iInitialSaveMillis) > 0) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Time11
### Patch Diff Hash-SHA-256:

1096ca05491c52d7428081c6a1c7574e213a637f97fb82c99c05c22af70ea5cb

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == (java.lang.Integer.MIN_VALUE)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Time11
### Patch Diff Hash-SHA-256:

52189e8342b3ee597001b68294cb35dd97770a6f089f851d036fa9ac3a223cf5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((YEAR_LIMIT) == 29) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Time11
### Patch Diff Hash-SHA-256:

faaf9fd709bba5c1ab2ffbd7cdf1e3a2dfdf0d76fb01c2e380aade9fcc981edb

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((YEAR_LIMIT) < 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Time11
### Patch Diff Hash-SHA-256:

43e1349307d2a757598d2a8c055cae2566a32a9a0544ab5a191bd63598cc49d2

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) < (iRules.size())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Time11
### Patch Diff Hash-SHA-256:

494c856f2d45bb3edfc7c34f795e93731d92ddea7c006faedae3758d26f9f527

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (((("UTC".equals(id)) && (id.equals(id))) && (size == 0)) && (size == 0)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Time11
### Patch Diff Hash-SHA-256:

bdc3d7a02bf6b02287f7eee9be5ffe30efeda0033eb336cd5aa37885ac351576

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((YEAR_LIMIT) == 2) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Time11
### Patch Diff Hash-SHA-256:

85ce8629a815eafe24ff064656dbbd928b913dddb80547e07fce9ad202674273

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (tailZone != null) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Time11
### Patch Diff Hash-SHA-256:

11f9f105728c1e7badff51e9cd67e6de84bbdb5fc4a009c926a288b01aa92dd5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iInitialNameKey) != null) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Time11
### Patch Diff Hash-SHA-256:

ba4c9ff2e5ee8264bf99e08a3011a8776603013db5514038c8881209d9bb3fab

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -164,7 +164,7 @@
 			} 
 			millis = rs.getUpperLimit(saveMillis);
 		}
-		if ((transitions.size()) == 0) {
+		if (saveMillis >= 2) {
 			if (tailZone != null) {
 				return tailZone;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Time11
### Patch Diff Hash-SHA-256:

34f61e474e35beb3b43473404089303ee4125c6fcb842d64f9c4003dfca3aabf

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(tailZone.getID())) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Time11
### Patch Diff Hash-SHA-256:

e33d91064f7361b8bdfbbb6c718264493bd8f564250cd2e214dc635f7b1d199a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((iInitialSaveMillis) == (iStandardOffset)) && (iInitialNameKey.equals(id))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Time11
### Patch Diff Hash-SHA-256:

f37f7508b1b51075656572cc447253358b194743ef9dacf7dbd31e45bb7a9b61

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size < ((nameKeys.length) - 1)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Time11
### Patch Diff Hash-SHA-256:

fb3ad87ad035d0758a35fc9be9618ac6e2f95dcc102e2c5e84b4f7edd91da5b0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iInitialSaveMillis) == 2) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Time11
### Patch Diff Hash-SHA-256:

c3efe12ce0bacda0ce571da999ea6f26435e3d048949a18f5c71a41af423a9aa

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((id.equals(id)) == false) && (("1".equals(id)) == false)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Time11
### Patch Diff Hash-SHA-256:

36fbe1663bbc5cb2afac15831cbc22c6d2aaf0a9baf91cfd096bc20f68118d7a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (size == (size - 1)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Time11
### Patch Diff Hash-SHA-256:

930c49bf8e10f9aac93b249f82ded63a0b162f3a0bf6b89e69536e81d4888e76

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (transitions.remove(org.joda.time.DurationFieldType.years())) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Time11
### Patch Diff Hash-SHA-256:

ca2401df8d697467886f8cd48ba815ab6bd5efef17fc98f89450d85ebb7db764

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (ruleSetCount < ruleSetCount) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Time11
### Patch Diff Hash-SHA-256:

9a8b90362f2f626acd0df9448e60145e17ff989fd4f92068991ad361407b795b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (chrono == null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Time11
### Patch Diff Hash-SHA-256:

358ce059230a2d270211b75f2bc0c4a06f76a62422d8beefe384440804cfc5ef

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (tailZone.isFixed()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Time11
### Patch Diff Hash-SHA-256:

7561e609ba1d99a500faf08c02ff605965648477cfa7ed15354fe569b240c1a2

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) > 1) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Time11
### Patch Diff Hash-SHA-256:

7c4a02f7cd0f3a89220e67c147f0be3b029eb999e68de998d9733832279f1ff9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if ((iStandardOffset) > 59) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Time11
### Patch Diff Hash-SHA-256:

d0dd3da11b9be67d89d09deb4004d359711677613c992b84fa569e100b2aa24a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) > (org.joda.time.MutableDateTime.ROUND_HALF_EVEN)) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Time11
### Patch Diff Hash-SHA-256:

4a1043b8c7316514d537ec27cc6ba6904cf7f544ef906ac1c61d5421a52d6fac

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if ((iStandardOffset) > 0) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Time11
### Patch Diff Hash-SHA-256:

103540d9b8ffaf9d1213ea6dfb3ad06eb4b97226d0226bce7c8ae1e431732486

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) > 7) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Time11
### Patch Diff Hash-SHA-256:

49fde2776e99e73de5828b35227690d4aa29a623aef125341c64d435a37c5fea

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((millis > millis) && ((saveMillis != saveMillis) || (!(id.equals(id))))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Time11
### Patch Diff Hash-SHA-256:

91e376369229674216288f0ffdfdaf014189977c7220eb1a5a287991964c8335

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((((iStandardOffset) >= 4) && (((id.charAt(0)) == 'P') || ((id.charAt(0)) == 'p'))) && (((id.charAt(1)) == 'T') || ((id.charAt(1)) == 't'))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Time11
### Patch Diff Hash-SHA-256:

d355b1dbde757cf8955a676ffee48ace36bb3efd979258e2c497d11e2b92479a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (id.regionMatches(true, iStandardOffset, id, 0, id.length())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Time11
### Patch Diff Hash-SHA-256:

56016d5b455708b6600353074c42eb89bc37e3ddaf13778aeaf8ea86ce40336d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (tailZone.isFixed()) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Time11
### Patch Diff Hash-SHA-256:

98fb1956c8e6107842b45adf642b8515dd290983f10b4ba47b29af5294003c0e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((id.length()) <= 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Time11
### Patch Diff Hash-SHA-256:

e9140570473715665dfd89203992a05d92cb81e847803d0bca396dd6b2578430

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(nameKeys[0])) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Time11
### Patch Diff Hash-SHA-256:

35aff9a2501af2aca3af4c395a4bdef623c049323e3994e1cfb794efcfaf92c6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == 3) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Time11
### Patch Diff Hash-SHA-256:

db622a68aaccd28abc2d8928a91383c5069713045e83d69f163b492470f9d4a5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (id.equals(chrono)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Time11
### Patch Diff Hash-SHA-256:

65eabbb811609bfea7f4adf40839a4a69cd33e80409b960488d1be2473fb641e

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((millis < millis) && (millis < millis)) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Time11
### Patch Diff Hash-SHA-256:

b3a9fe68052dd75145ff0bbbfed25f852f5b1c40abe9727cd180823586d50fa3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((iStandardOffset) < (iStandardOffset)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Time11
### Patch Diff Hash-SHA-256:

85e5fccaa554ba7d0a7b90d844e511a2602d35dcb343b8bee0c6a4d4a8ecc22d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && (saveMillis < saveMillis)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Time11
### Patch Diff Hash-SHA-256:

28eedf7123023d6be10c17a17d8c7c62d34aa5583284109913b68c0e54d8ac47

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis < 0) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Time11
### Patch Diff Hash-SHA-256:

f87104ff4440855eb560c5a257b0dc47dee7f09c0cddec6527f2a0a8a5bfe7c9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iStandardOffset) == (-1)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Time11
### Patch Diff Hash-SHA-256:

7136a650684ecb932eb10ae84db8307d0ecc9d4fcb093f8efdf016b98ac867b0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iStandardOffset) == 0) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Time11
### Patch Diff Hash-SHA-256:

d565416e8fdd1ed86f57cf158910beed57e364af34e8110a20f5d5e0fbbb4ed7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((iStandardOffset) == 0) || ((iStandardOffset) == 1)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Time11
### Patch Diff Hash-SHA-256:

95722f6539f8ee52925f79d3937df8b28fb130b354b6a7c55ce25cec84525400

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.equals(zoneNameData[4])) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Time11
### Patch Diff Hash-SHA-256:

b55848f86ec21edc2c88e8e16c14894f4ca8ec5b6bb91c7884c19a65bd155385

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (millis > millis) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Time11
### Patch Diff Hash-SHA-256:

ce2665b70a01cfa02294c4519cc92d19f5945ca500b1f750a715a26d214c4765

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id == null) || (((id.length()) < 3) && (!("??".equals(id))))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Time11
### Patch Diff Hash-SHA-256:

2880536b869c78e983e1fcaeebd6caffa1c5ee146d139e804a8fcf7769c583b8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((size == 0) && (size == 0)) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Time11
### Patch Diff Hash-SHA-256:

f9abbc6e9cebd764c7c6d97745bb6bc540cf6128083d47ee804a3c9bebfe002b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis > saveMillis) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Time11
### Patch Diff Hash-SHA-256:

0c7e9aea38bc9797765a7b9edc9c13754168a66b06338718e5674b92383dd3a9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (false) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Time11
### Patch Diff Hash-SHA-256:

e4dcb19ca10401dc7346731f101d092164519d2d5c402cb138c76944054d7eda

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) >= 0) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Time11
### Patch Diff Hash-SHA-256:

c3ae9a079fd92e5991dea80a9bfcf209a6fcb2dc5c52836e88717d681c3dbda3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) > (iStandardOffset)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Time11
### Patch Diff Hash-SHA-256:

862b18963e351b96a7c90d9c852c5d1a487a332c318b2d7443aa64cd50d6e609

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (iRules.isEmpty()) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Time11
### Patch Diff Hash-SHA-256:

09baed98a9869cd21378628d588f343be92cd6c19f29b94beeff3122192ae87a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (iRules.remove(org.joda.time.DurationFieldType.minutes())) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Time11
### Patch Diff Hash-SHA-256:

d4d99669a975b80d718d7d83d8f2f4b40a7f6261495e7c1dbab975d49589faa9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == 0) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Time11
### Patch Diff Hash-SHA-256:

1fe8273d66a1cde79177ad3001a2fd4fb906f64cfeb190788e290b52ac95b830

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (id == null) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Time11
### Patch Diff Hash-SHA-256:

8152e67d237800881003cbeebc0ba8786e028b3025426a5777548c3a8dedb14b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if ((iStandardOffset) > 1) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Time11
### Patch Diff Hash-SHA-256:

e251985b2546c4de5549cff93cf058e8df168bc1e6e2185d4d7083aac306592c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) < 11) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Time11
### Patch Diff Hash-SHA-256:

c76a37b0b57557fc0b95e496b1e4eaefb56d82f511404220770dc01009b526c6

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -723,7 +723,7 @@
 					nextMillis = next;
 				}
 			} 
-			if (nextRule == null) {
+			if ((iStandardOffset) > 0) {
 				return null;
 			}
 			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Time11
### Patch Diff Hash-SHA-256:

2d17a58cf09850839e36e9b775220d9ca0d43d6c841621f8f3da808ac749ba8b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (id.startsWith("-")) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Time11
### Patch Diff Hash-SHA-256:

b04e28645d791178c2129b919284d41f4695c8366e3bde813835854ae3593fa0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((iRules) == null) || ((iRules.size()) == 0)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Time11
### Patch Diff Hash-SHA-256:

d4e7bb9eadb5879785a17ab925fe7783e6aaf2b0c04704c8432c1d076966b02f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((id == null) || (id == null)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Time11
### Patch Diff Hash-SHA-256:

a9d1550c0516ba097119d13203bffbf26a3369d1889ba012117a5f41a4518601

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (((id.charAt(1)) == 'T') || ((id.charAt(1)) == 't')) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Time11
### Patch Diff Hash-SHA-256:

c82d20b8edb9b389980014232ceb2d02f6e435fdab7a5891ec6870f000b2ba34

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((millis << (64 - 30)) >> (64 - 30)) == millis) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Time11
### Patch Diff Hash-SHA-256:

5326b8d976e2352144ac311bfd941f674a664de773e0e9ca87679ad82b798aa9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) == (-1)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Time11
### Patch Diff Hash-SHA-256:

ff11f4962f9dfccdb838392c28cfe2e75a77e916e767e860963790c2c4a18c3b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (chrono instanceof org.joda.time.chrono.StrictChronology) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Time11
### Patch Diff Hash-SHA-256:

594c7ee204fa8ab9d0d63e4bd7a91f55a9cf1b26bd3feb292734397a1aa13ed9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (((nameKeys != null) && (size == 5)) && (id.equals(nameKeys[0]))) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Time11
### Patch Diff Hash-SHA-256:

97bc573b2e6ccb5bf127a55d2ffb7e4455122b384c7bfb42be3b10118229e3c7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (org.joda.time.DateTimeZone.UTC.equals(org.joda.time.DateTimeZone.UTC)) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Time11
### Patch Diff Hash-SHA-256:

c1855633f1a169c75aa6f3e4e05e74247eda57d9372e4e89f2237c81d8403960

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((iStandardOffset) == 2) && ((iStandardOffset) == 29)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Time11
### Patch Diff Hash-SHA-256:

531d552c303682a9ba3767f00802e2bb4ed5213284d16f8356a8bc969c8f1d7c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (!outputID) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Time11
### Patch Diff Hash-SHA-256:

b83a8c2ba2d9e0dd98ecb59f610acf73b79317d23f1d67f49a78a1289dd04850

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if ((iStandardOffset) >= 9) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Time11
### Patch Diff Hash-SHA-256:

e60ceaabdea2436da9eb75bee75c90c19f7613cae307c6c5bcd64fbcb916fa93

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((id.startsWith("GMT+")) || (id.startsWith("GMT-"))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Time11
### Patch Diff Hash-SHA-256:

8f7f07e800f650ca6831a226c9b6fb1bef598edce83b12d81b8d9efac92e6603

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((millis < 0) && (millis > 0)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Time11
### Patch Diff Hash-SHA-256:

a612f8a5ced444616acd260575f91fb9b6efeadb95b63ab8c6b5747614168a41

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((id.length()) < 3) && (!("??".equals(id)))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Time11
### Patch Diff Hash-SHA-256:

d8ac22285371a4b59a1ac9754a4d167be87eb5bd392dc84eb32b0d51e87a92a1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (("??".equals(id)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Time11
### Patch Diff Hash-SHA-256:

9905c3225c32a1e3b694a1bd0472b28c95a1d1251a228b9be0bc79838b172fd2

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((tailZone == null) && ((tailZone == null) && (ruleSetCount == (ruleSetCount - 1)))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Time11
### Patch Diff Hash-SHA-256:

6c0e0a69d1742deb8492bd3cc925bae0761d6aed4a4691fc735945af5fa0af31

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -985,7 +985,7 @@
 			}
 			if (tailZone != null) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
-					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
+					if (last == null) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
 					if ((tailZone.iStartRecurrence.getSaveMillis()) > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Time11
### Patch Diff Hash-SHA-256:

59badcab8ffda8bffae6532c4e73760a5cbcf9a0d96cf70452fb2898051cd278

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (((transitions.size()) == 0) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Time11
### Patch Diff Hash-SHA-256:

dc542da1ea75050bcff6c3fd4e51f9bee13c11750e82621f2b4e9d69561bb7d5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((iStandardOffset) == 2) && ((iStandardOffset) == 29)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Time11
### Patch Diff Hash-SHA-256:

85992a445a51576cb63af9ee2ec4bd882810fb59f7e5d3164b0136e5e8f29050

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((id.charAt(0)) == '#') {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Time11
### Patch Diff Hash-SHA-256:

3b6264531f0831ef5cba510f3df64c19bf79629d3384048688217787b4de7390

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (("UTC".equals(id)) && (id.equals(id))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Time11
### Patch Diff Hash-SHA-256:

42bfb9175da0cc0c9670e5758c541364d383cb52c0b4ba47207c46d10c14ada1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((("UTC".equals(id)) && (id.equals(id))) && ((iStandardOffset) == 0)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Time11
### Patch Diff Hash-SHA-256:

7f65c89503d9fffbf5d77bb6a13c8108cdc68f16b8f5711021dd413f4ed96dc2

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((id == null) || (((id.length()) < 3) && (!("??".equals(id))))) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Time11
### Patch Diff Hash-SHA-256:

2333820feb8457fc76e809b3d6172adccd45605d7e0ad0214148b005a14cc2a3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) < (iStandardOffset)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Time11
### Patch Diff Hash-SHA-256:

b1e0569054f4c0df7091b77e7ca1c9c2e99925fec375646b56921af2516d2b15

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (id.trim().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Time11
### Patch Diff Hash-SHA-256:

40358a79f95f5de2a3960f406b0e5b306229bafd79d2603ce6d732a68a49d2a9

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == (-1)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Time11
### Patch Diff Hash-SHA-256:

67f646f12897be2aaf6d22fa7e65d63b9e678fb4d47dd3e457b79eb184648d9c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -164,7 +164,7 @@
 			} 
 			millis = rs.getUpperLimit(saveMillis);
 		}
-		if ((transitions.size()) == 0) {
+		if ((--saveMillis) >= 0) {
 			if (tailZone != null) {
 				return tailZone;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Time11
### Patch Diff Hash-SHA-256:

03608c3b9c69f3ab497f63b1fb2a896552cc714bf742f68e8627fd51ad5c8b06

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iStandardOffset) < (iStandardOffset)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Time11
### Patch Diff Hash-SHA-256:

fa34f22d7e8639d54adad5c8303317b5d70aaca2b907644475b708373ef8ceee

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) == (-1)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Time11
### Patch Diff Hash-SHA-256:

129d6b4a15b9749b02ddc6c35928f25007aa400dd981d94e4f6f8d189db56bdc

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if (((id.length()) == 0) || ((id.charAt(0)) == '#')) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Time11
### Patch Diff Hash-SHA-256:

08dfdeffeeb3a138cabe742a102b9802cb35ed2206223d54292f1ec5093e4f28

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iUpperYear) < (iUpperYear)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Time11
### Patch Diff Hash-SHA-256:

61f78dff2db917ef7e704bdf399bd0cf8b8c0349d3cc81c76f0b39df79c49a12

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == 2) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Time11
### Patch Diff Hash-SHA-256:

6f446c578bd9d183d0a6d9eb2ebd30b424b7cd59747bab33a261db449c766918

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iUpperYear) < (iUpperYear)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Time11
### Patch Diff Hash-SHA-256:

1b2bc73e5ff8c49bca9bcebc3ff0dedd7d0738f17bde666a3238047a308ac99a

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((endRule.getToYear()) == (iStandardOffset)) && ((startRule.getToYear()) == (iStandardOffset))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Time11
### Patch Diff Hash-SHA-256:

e5e07ea70c0c657f008d7bf3f9cbe7eefaaf64a2d27dc88a2d28383bb17c8da1

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) < (iRules.size())) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Time11
### Patch Diff Hash-SHA-256:

990c18e4eb8a3b83169329802b3730b4e6697091f70969b333eeb1ac45c0b50f

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.length()) < 3) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Time11
### Patch Diff Hash-SHA-256:

90cf6a247cbb7d65bdff8515c9f944a38448184aeb31067192cecd22ec07c212

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if ((millis != millis) && (i == (ruleSetCount - 1))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Time11
### Patch Diff Hash-SHA-256:

cdb7d4b0b1cc30c0d273187120221da81757af923eff4e304f09e885e3324451

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.indexOf('/')) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Time11
### Patch Diff Hash-SHA-256:

553bc3e5242662d2a00d063bda3fbe23e4d4c701f09e002c1b77a734d2a5cf45

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((id.indexOf("%s")) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Time11
### Patch Diff Hash-SHA-256:

5cd454d766cbde6489301525270bc31c771efb7a5d49a45c588ee998fb66dfd0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -984,7 +984,7 @@
 				}
 			}
 			if (tailZone != null) {
-				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
+				if (tailZone.getID().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Time11
### Patch Diff Hash-SHA-256:

79533f955d4e5c0d047059459b49df1dec2d7cae44b6b9aad5bec70bd796bf4c

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if (((("UTC".equals(iInitialNameKey)) && (iInitialNameKey.equals(iInitialNameKey))) && ((iStandardOffset) == 0)) && ((iInitialSaveMillis) == 0)) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Time11
### Patch Diff Hash-SHA-256:

95472e1af32c2a2b3fec482801435d69963f60924dc828d506471258eb5cb499

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == 2) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Time11
### Patch Diff Hash-SHA-256:

caefe22a67ec2dacc529b00da7c44eeff255d7ee04fd188dddcf8a19458a082d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((iStandardOffset) == ((iStandardOffset) - 1)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Time11
### Patch Diff Hash-SHA-256:

704e3cf3a952f13935e728219b8365b4d6d9a563b5fdb788b363dc7b4ca992b5

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == 1) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Time11
### Patch Diff Hash-SHA-256:

803ade6d7835a3773cca108e7e73bf81926dcc5717fc9e9f92f998c057e32b45

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((id.equals("maximum")) || (id.equals("max"))) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Time11
### Patch Diff Hash-SHA-256:

ea538f1870cb4beba60927e78126db231b0199e8c40d39083dcffc330011036b

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((iStandardOffset) == (~(iStandardOffset))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Time11
### Patch Diff Hash-SHA-256:

25632ae7686902c563f36507c6aebef03db885d386c9a30b59fbc7b91ed9ac83

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if (((("UTC".equals(iInitialNameKey)) && (iInitialNameKey.equals(iInitialNameKey))) && ((iStandardOffset) == 0)) && ((iInitialSaveMillis) == 0)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Time11
### Patch Diff Hash-SHA-256:

658ccfcc05775dc24a2c254bce3a1f00c0ed7ed6eb67a6bcac36a026872bde7d

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == (~saveMillis)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Time11
### Patch Diff Hash-SHA-256:

2690f2c7f4de6ab3d467da49daf0c14b9335b9aca241d4c5650f54f8b5293564

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (saveMillis == (saveMillis - 1)) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Time11
### Patch Diff Hash-SHA-256:

40b46244e42bb3e2a9e369a87df3187b6793066268b40d375dab9db68343b4c8

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -749,7 +749,7 @@
 			if ((iRules.size()) == 2) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
-				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
+				if ((id == null) || (((id.length()) < 3) && (!("??".equals(id))))) {
 					return new org.joda.time.tz.DateTimeZoneBuilder.DSTZone(id, iStandardOffset, startRule.iRecurrence, endRule.iRecurrence);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Time11
### Patch Diff Hash-SHA-256:

ab1dd944d3e3ef92e5e8f217e054cbf0d060ee9bd71dd2c547c1722b1c9989a0

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -158,7 +158,7 @@
 				}
 				millis = next.getMillis();
 				saveMillis = next.getSaveMillis();
-				if ((tailZone == null) && (i == (ruleSetCount - 1))) {
+				if (("UTC".equals(id)) && (id.equals(id))) {
 					tailZone = rs.buildTailZone(id);
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Time11
### Patch Diff Hash-SHA-256:

ecdd7cc1f972e4a1de5cd58c1e4eea5f79681f77898715fbb77e2d859f4e19e7

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -983,7 +983,7 @@
 					
 				}
 			}
-			if (tailZone != null) {
+			if ((id.equals("maximum")) || (id.equals("max"))) {
 				if (tailZone.iStartRecurrence.getNameKey().equals(tailZone.iEndRecurrence.getNameKey())) {
 					if (org.joda.time.tz.ZoneInfoCompiler.verbose()) {
 						java.lang.System.out.println(("Fixing duplicate recurrent name key - " + (tailZone.iStartRecurrence.getNameKey())));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Time11
### Patch Diff Hash-SHA-256:

c65b47c9164a3f44f17c8ab4797989caa6da80ce687a80f9814d6a2149903cc4

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -746,7 +746,7 @@
 		}
 
 		public org.joda.time.tz.DateTimeZoneBuilder.DSTZone buildTailZone(java.lang.String id) {
-			if ((iRules.size()) == 2) {
+			if ((("UTC".equals(id)) && (id.equals(id))) && ((iStandardOffset) == 0)) {
 				org.joda.time.tz.DateTimeZoneBuilder.Rule startRule = iRules.get(0);
 				org.joda.time.tz.DateTimeZoneBuilder.Rule endRule = iRules.get(1);
 				if (((startRule.getToYear()) == (java.lang.Integer.MAX_VALUE)) && ((endRule.getToYear()) == (java.lang.Integer.MAX_VALUE))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Time11
### Patch Diff Hash-SHA-256:

8fac51c4018fcd1c79f60c9115049ff2787ee8b1f5a3de89db6ac01aa04458c3

### Patch Diff:
```
--- /original/org/joda/time/tz/DateTimeZoneBuilder.java	
+++ /fixed/org/joda/time/tz/DateTimeZoneBuilder.java	
@@ -726,7 +726,7 @@
 			if (nextRule == null) {
 				return null;
 			}
-			if ((chrono.year().get(nextMillis)) >= (org.joda.time.tz.DateTimeZoneBuilder.RuleSet.YEAR_LIMIT)) {
+			if ((iStandardOffset) >= 0) {
 				return null;
 			}
 			if ((iUpperYear) < (java.lang.Integer.MAX_VALUE)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Time4
### Patch Diff Hash-SHA-256:

5e6183f8b1b74ed58a48978416abab380733ae4b7de4313012ebf4fee4a87f97

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (getMinimumValue(instant, values)) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

3057246c793ee2b3aebd0a497f58ff6b45eb6757ed5cd32dd2810e6d08b493cf

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return instant.size();
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

0af836cf2f409b449c0a4e20c1d525484fc69bc69e1972e20be1a8e2e4f36500

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (getMinimumValue()) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

cb0d3b11799ce47cee9c2b58cc2e7d240ce770833dbc2c9bdfece596e75e07b9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (instant.size()) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Time4
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

3aa83f82f2c6e1bc51fc1936a358fef5301b9790b82c57323600e3cdb75f55fc

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue(instant, values);
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Time9
### Patch Diff Hash-SHA-256:

723f42bb18c6dd2e7d51c6abc26b55a0c2cd412cb18853891f86c77c7a43d378

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -124,7 +124,7 @@
 
 	public static org.joda.time.DateTimeZone forOffsetMillis(int millisOffset) {
 		java.lang.String id = org.joda.time.DateTimeZone.printOffset(millisOffset);
-		return org.joda.time.DateTimeZone.fixedOffsetZone(id, millisOffset);
+		return org.joda.time.DateTimeZone.forID(id);
 	}
 
 	public static org.joda.time.DateTimeZone forTimeZone(java.util.TimeZone zone) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Time7
### Patch Diff Hash-SHA-256:

602b6cf185f56d4e2acd610c0cb033022de244f42fb8913d894e8a3f1d4985c1

### Patch Diff:
```
--- /original/org/joda/time/format/DateTimeFormatter.java	
+++ /fixed/org/joda/time/format/DateTimeFormatter.java	
@@ -247,7 +247,7 @@
 		org.joda.time.Chronology chrono = instant.getChronology();
 		long instantLocal = instantMillis + (chrono.getZone().getOffset(instantMillis));
 		chrono = selectChronology(chrono);
-		int defaultYear = chrono.year().get(instantLocal);
+		int defaultYear = chrono.year().get(instantMillis);
 		org.joda.time.format.DateTimeParserBucket bucket = new org.joda.time.format.DateTimeParserBucket(instantLocal, chrono, iLocale, iPivotYear, defaultYear);
 		int newPos = parser.parseInto(bucket, text, position);
 		instant.setMillis(bucket.computeMillis(false, text));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Time18
### Patch Diff Hash-SHA-256:

f5064eb5211b4981b2cd1c3fa20108da5f8adb0ca0f0258b9ed3de770868107a

### Patch Diff:
```
--- /original/org/joda/time/chrono/BasicGJChronology.java	
+++ /fixed/org/joda/time/chrono/BasicGJChronology.java	
@@ -41,7 +41,7 @@
 	}
 
 	int getDaysInYearMonth(int year, int month) {
-		if (isLeapYear(year)) {
+		if ((year & 3) == 0) {
 			return org.joda.time.chrono.BasicGJChronology.MAX_DAYS_PER_MONTH_ARRAY[(month - 1)];
 		}else {
 			return org.joda.time.chrono.BasicGJChronology.MIN_DAYS_PER_MONTH_ARRAY[(month - 1)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---