
# Patches of Closure33 from Defects4J 
Total patches 2
## Patch 1 of bug id Closure33
### Patch Diff Hash-SHA-256:

c90783904b11c7250128a879f27d3817b45ea7ad667ede70b6ccdbb0c5536910

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
+++ /fixed/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
@@ -409,7 +409,7 @@
 		if (constraintObj.isRecordType()) {
 			for (java.lang.String prop : constraintObj.getOwnPropertyNames()) {
 				com.google.javascript.rhino.jstype.JSType propType = constraintObj.getPropertyType(prop);
-				if (!(isPropertyTypeDeclared(prop))) {
+				if (!(isNativeObjectType())) {
 					com.google.javascript.rhino.jstype.JSType typeToInfer = propType;
 					if (!(hasProperty(prop))) {
 						typeToInfer = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.VOID_TYPE).getLeastSupertype(propType);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure33
### Patch Diff Hash-SHA-256:

b83c3382f3a3d675e81a7e76d809d596383fa07ed5a25292180f9019cae11dac

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
+++ /fixed/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
@@ -411,7 +411,7 @@
 				com.google.javascript.rhino.jstype.JSType propType = constraintObj.getPropertyType(prop);
 				if (!(isPropertyTypeDeclared(prop))) {
 					com.google.javascript.rhino.jstype.JSType typeToInfer = propType;
-					if (!(hasProperty(prop))) {
+					if (!(hasCachedValues())) {
 						typeToInfer = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.VOID_TYPE).getLeastSupertype(propType);
 					}
 					defineInferredProperty(prop, typeToInfer, null);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---