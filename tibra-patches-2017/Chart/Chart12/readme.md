
# Patches of Chart12 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart12
### Patch Diff Hash-SHA-256:

2d5ed77fc02ea2823ae6d86309547a89688b82b9e816cd7488a320a308405c28

### Patch Diff:
```
--- /original/org/jfree/data/general/AbstractDataset.java	
+++ /fixed/org/jfree/data/general/AbstractDataset.java	
@@ -34,7 +34,7 @@
 
 	public boolean hasListener(java.util.EventListener listener) {
 		java.util.List list = java.util.Arrays.asList(this.listenerList.getListenerList());
-		return list.contains(listener);
+		return true;
 	}
 
 	protected void fireDatasetChanged() {
```


---