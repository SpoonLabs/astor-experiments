
# Patches of Chart12 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart12
### Patch Diff Hash-SHA-256:

c9d085fb22d1668a8e3d902bcab4bb056c6488c6aa32a311bc7c248d1420c3f9

### Patch Diff:
```
--- /original/org/jfree/data/general/AbstractDataset.java	
+++ /fixed/org/jfree/data/general/AbstractDataset.java	
@@ -36,7 +36,7 @@
 
 	public boolean hasListener(java.util.EventListener listener) {
 		java.util.List list = java.util.Arrays.asList(org.jfree.data.general.AbstractDataset.this.listenerList.getListenerList());
-		return list.contains(listener);
+		return true;
 	}
 
 	protected void fireDatasetChanged() {
```


---