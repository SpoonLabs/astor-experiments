
# Patches of Math56 from Defects4J 
Total patches 1
## Patch 1 of bug id Math56
### Patch Diff Hash-SHA-256:

4e48f676c913f47c8f00fbe1bd698915df01ada76cb19b6c68966919f951efb7

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MultidimensionalCounter.java	
+++ /fixed/org/apache/commons/math/util/MultidimensionalCounter.java	
@@ -110,6 +110,10 @@
 		int idx = 1;
 		while (count < index) {
 			count += idx;
+			while (count < index) {
+				count += idx;
+				++idx;
+			} 
 			++idx;
 		} 
 		--idx;
```


---