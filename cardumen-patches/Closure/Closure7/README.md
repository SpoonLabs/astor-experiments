
# Patches of Closure7 from Defects4J 
Total patches 2
## Patch 1 of bug id Closure7
### Patch Diff Hash-SHA-256:

638bdcaba8fbaa48127d1fc02728db3dbcb94355cc146b6de4ef888385e4c909

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/type/ChainableReverseAbstractInterpreter.java	
+++ /fixed/com/google/javascript/jscomp/type/ChainableReverseAbstractInterpreter.java	
@@ -452,7 +452,7 @@
 
 		@java.lang.Override
 		public com.google.javascript.rhino.jstype.JSType caseObjectType(com.google.javascript.rhino.jstype.ObjectType type) {
-			if (value.equals("function")) {
+			if (matchesExpectation("function")) {
 				com.google.javascript.rhino.jstype.JSType ctorType = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.U2U_CONSTRUCTOR_TYPE);
 				return (resultEqualsValue) && (ctorType.isSubtype(type)) ? ctorType : null;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure7
### Patch Diff Hash-SHA-256:

e4930e70055f9bb3e87e97bdb372adfd9a6546a14c23f3855ae40dbaf04b14ed

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -33,7 +33,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(((("Both types must be null, or both must be non-null " + b) + ",") + a), ((b == null) == (a == null)));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---