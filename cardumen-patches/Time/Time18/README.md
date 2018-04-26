
# Patches of Time18 from Defects4J 
Total patches 1
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