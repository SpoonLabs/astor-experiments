
# Patches of Chart12 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart12
### Patch Diff Hash-SHA-256:

be0ea22e866ab3d164c2ea6d2fc9ce79a276ff38483417c30ec8f7315f266b17

### Patch Diff:
```
--- /original/org/jfree/data/general/AbstractDataset.java	
+++ /fixed/org/jfree/data/general/AbstractDataset.java	
@@ -36,7 +36,7 @@
 
 	public boolean hasListener(java.util.EventListener listener) {
 		java.util.List list = java.util.Arrays.asList(org.jfree.data.general.AbstractDataset.this.listenerList.getListenerList());
-		return list.contains(listener);
+		return !(listener instanceof org.jfree.data.general.Series);
 	}
 
 	protected void fireDatasetChanged() {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---