
# Patches of Lang27 from Defects4J 
Total patches 164
## Patch 1 of bug id Lang27
### Patch Diff Hash-SHA-256:

6d30fddbe3e9ae7904b95098c5f4e85101ca747fdf2a7f3e6336a66b568a0051

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang27
### Patch Diff Hash-SHA-256:

07b28111b32b54c42ca1fc1b37a027c31cb56e8f15253ebcb8f1f014ca213ece

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (-1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang27
### Patch Diff Hash-SHA-256:

8b34271669698b27bdc9bfbf828469238a249b1a3eb8d60817b724a0bbc9ea3b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos > (-1)) && (expPos < ((str.length()) - 1))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang27
### Patch Diff Hash-SHA-256:

9f0915b63a69b88b966d9e6357b7870f7723f12f4f78d26105ac2470f7b9d0c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang27
### Patch Diff Hash-SHA-256:

b0447430ab388be7f93b44c6d0f19fb7ac12814baa1a625d584eb4b13d0ccf73

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos < expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang27
### Patch Diff Hash-SHA-256:

6654d553dd78d8e0fac7a941150c00696f2369131c1dd0e2af6418897abf929c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((FLOAT_ONE.floatValue()) == 0.0F) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang27
### Patch Diff Hash-SHA-256:

c6236829ca1c0e5e8870c48539d9ded8d8b376949bacfb6eb93f785ba9aeab98

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang27
### Patch Diff Hash-SHA-256:

eb9f791ac9a4b9bba5a042f7410d8c5a9dbbd51914e0f1d5a7d5bdff9759566c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE.floatValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Lang27
### Patch Diff Hash-SHA-256:

d727b831eeb149f6ca2bac2dbfd26d323d51e35218472224fd36d2353cb25598

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_MINUS_ONE.doubleValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Lang27
### Patch Diff Hash-SHA-256:

3b72f04ca42e7be581ff3ca85a9e9f9c172970213f2d23622c2b89d21faaa864

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Lang27
### Patch Diff Hash-SHA-256:

1c1452af550f1feb7ed5144d343df7d15740c8942cf02833f9973c3778af3b6b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.startsWith("0x")) || (str.startsWith("-0x"))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Lang27
### Patch Diff Hash-SHA-256:

5cbd6fccbb919c1e71680341da225afa91aeae0cf48bd7942ec0853edad51ef7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((FLOAT_MINUS_ONE.floatValue()) == 0.0F) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Lang27
### Patch Diff Hash-SHA-256:

63ed08a4d12ebe54a423a351276fa55c726e335be7f3da340cdf31a35361c977

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_MINUS_ONE.floatValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Lang27
### Patch Diff Hash-SHA-256:

d54948a45e17945fb64f5f008ac0945ee665a8247f650cc3b0c38f3c603d1d3d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (decPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Lang27
### Patch Diff Hash-SHA-256:

5b0d7f9f7bde3aed4e667c3c39c24e847027804fafc1f78403000864fb7443eb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE.doubleValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Lang27
### Patch Diff Hash-SHA-256:

4daeeaf8e74e8253ed7689b08fd9e53d8bfc960674c1e3b1b9b49cdb423d908d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (expPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Lang27
### Patch Diff Hash-SHA-256:

2e408679a955f0cdc6cb21ab0c79cd5e6372dac56619ebb09ab331d53a097106

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > (expPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Lang27
### Patch Diff Hash-SHA-256:

9228e19b1d23372728873ab4821efdad4684f8276f72be5486fe6708d402c433

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (false) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Lang27
### Patch Diff Hash-SHA-256:

0feb107356d724b98c3b70c9e2bf2f8ece6973804ace393caf13e486d1741ff0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == (expPos - 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Lang27
### Patch Diff Hash-SHA-256:

3e47b231cc381380b150c183edcbd3b549d5c3537e233d8019fbcff06834ab99

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (BYTE_ONE.equals(FLOAT_ONE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Lang27
### Patch Diff Hash-SHA-256:

b8cf26b4e341c749ab2b58cfe77e27d420bdd225bf3677fbe3e14c0b5b3284fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 255) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Lang27
### Patch Diff Hash-SHA-256:

46597dcbb4fc10d343819818a3382c86b7cf138c545e39acf2802513f9bcca8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Lang27
### Patch Diff Hash-SHA-256:

cdca9d499dd5b055fe9752b715532672abfd7d7d76313606ddbc216e0193ab8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 56320) && (lastChar <= 57343)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Lang27
### Patch Diff Hash-SHA-256:

51b8dd26f88678f1cc6607abea8d0deb219690c5d68a405fa7fa202ed145a9c2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((decPos < decPos) && (expPos < expPos)) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Lang27
### Patch Diff Hash-SHA-256:

a34fb30678a0dc06428f6b62113aeb4e9b1c588ee2803297b1443a6f7f7d317b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Lang27
### Patch Diff Hash-SHA-256:

6eba9e54b28e31d71ca35c74e2f0a6898ddbda01524b0f1b6955748b7f24a828

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((LONG_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Lang27
### Patch Diff Hash-SHA-256:

a45b9d0ba7d1daa1aa823d181ac780d9cd45e5cb9fa203a20081e2ed90d30ad4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'S') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Lang27
### Patch Diff Hash-SHA-256:

b79b6314485f9afd5a62dd4e772d088b29bdafce4db3dd1228a1163c0fb3a121

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (INTEGER_ZERO.equals(FLOAT_ONE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Lang27
### Patch Diff Hash-SHA-256:

85b120b56729bc925b3b971c62e578371d71c0b6cfc7c5df332b910e6040c7e8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 56192) && (lastChar <= 56319)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Lang27
### Patch Diff Hash-SHA-256:

3add71810723f4ccdd88240f5214534f3b8c875b6d428d10e5d374d950df74b9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (SHORT_ZERO.getClass().getName().equals(FLOAT_MINUS_ONE.getClass().getName())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Lang27
### Patch Diff Hash-SHA-256:

99aadb852c234063a2e75485949356e0a4071fef8635d71a78a5a6dfcfdc8c9c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Lang27
### Patch Diff Hash-SHA-256:

34b89312985d2b99c58b4fe6b6d58b8b086f9998232dfc491bd9eb0f51df9d47

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 12) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Lang27
### Patch Diff Hash-SHA-256:

17626ea577ac5a2ccafcd45c823b43b61475ce310facf96fa4c38aacbc93823a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Lang27
### Patch Diff Hash-SHA-256:

47c19802961a08554fc305e79a1bfa2aa42560505be92544cbfa486eed80b118

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Lang27
### Patch Diff Hash-SHA-256:

138a586d9db1b5efedb79c8ab98025feb879f94fc85e41e75d336ff203d1c977

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'R') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Lang27
### Patch Diff Hash-SHA-256:

cabb6af60ec5f2db25eb482c2273c428cbe6e574abcda0a46b8318c8aad9bc34

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'Y') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Lang27
### Patch Diff Hash-SHA-256:

2c5ff2da473855f1ff6cc176ee35a8dc33548caef13d81558a7a1005b6b90b67

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'X') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Lang27
### Patch Diff Hash-SHA-256:

7887def65c84dfdcd4e4066b70ea3a999684b2d83e980eeadf538a71cc4ea6b6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (java.lang.Character.isTitleCase(lastChar)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Lang27
### Patch Diff Hash-SHA-256:

205cac264e3db7507c84df47790aec16a9374262283412c82f19109def779828

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 64) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Lang27
### Patch Diff Hash-SHA-256:

749eeb3457c2d8fd87b5878fc3d5f3883b241bea1c563b0a0991076943c6c52f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos >= 15) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Lang27
### Patch Diff Hash-SHA-256:

2bb99468d28dd84a111ebcf1d7e7fb5f121e1cf9accab1c5e274cf91224735bb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 4) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Lang27
### Patch Diff Hash-SHA-256:

6f28a0757ac51052a012f3c8e319e1d1dc5a95c2adb1d12020e0cbdf056bdf7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'o') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Lang27
### Patch Diff Hash-SHA-256:

8dee78b6d04479b439748981ae5bbd7ad8ff1ccb263432dac5dee788b9c86deb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((SHORT_MINUS_ONE) == null) || ((DOUBLE_MINUS_ONE) == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Lang27
### Patch Diff Hash-SHA-256:

930895ecb46526c1522de1a124e1abc09a57548ca786e31842dcd36ae0a57b11

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (INTEGER_MINUS_ONE.equals(BYTE_ZERO)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Lang27
### Patch Diff Hash-SHA-256:

e3c6b89453d5ec2dbfc7e27e5b179ae3259256204da6bf18c9ca06be7b3872bf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((decPos > 0) && (decPos > 0)) && (decPos >= decPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Lang27
### Patch Diff Hash-SHA-256:

197d39b1a07d51d020b838dd0e05743bb013aa80e70ab5f2a70183faa4fea6d0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos + decPos) > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Lang27
### Patch Diff Hash-SHA-256:

a29c8632c843b923880744ba0862ada14f1ae0b960ff379bcf4b9a5a881f29be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Lang27
### Patch Diff Hash-SHA-256:

5369db697f55d9755c3269ffe7f63e12bd9c35491297477e6b7ff95aa1274bba

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 't') || (lastChar == 'T')) && ((lastChar == 'r') || (lastChar == 'R'))) && ((lastChar == 'u') || (lastChar == 'U'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Lang27
### Patch Diff Hash-SHA-256:

40889794fa72d204ea46dc00cc5460a19aa46e9e26926bbd60a0fba6c00a8bbc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (-1)) && (decPos != decPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Lang27
### Patch Diff Hash-SHA-256:

ce5d642f98fffdb9245c27c56eec6dc60db4074e97bd896b87c24b37f4d37797

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (SHORT_ZERO.equals(FLOAT_ZERO)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Lang27
### Patch Diff Hash-SHA-256:

919b9d94e92af5a561db7e2a8d5e968f3cb49375c9a547ea4fafc75e548d1e2c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar < 32) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Lang27
### Patch Diff Hash-SHA-256:

e13e344d737d254e1b5e10ab98367d342aa5b26d28bb87de74b218aff19e3ffb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Lang27
### Patch Diff Hash-SHA-256:

b40fa5fe122d4f7109bcf5e27286068b8af0842d15a213428148316f4fffc012

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 64) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Lang27
### Patch Diff Hash-SHA-256:

ecee54f9ee95ee2f36dac154f6f0ae39c76c68ebde2ca7b74e4db4464d4ffc91

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) && ((lastChar == 'l') || (lastChar == 'L'))) && ((lastChar == 's') || (lastChar == 'S'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Lang27
### Patch Diff Hash-SHA-256:

1ad11ffb22c93c82ff3f0a9b144483870be1eb8020658ee29a8cffe71881127d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos < decPos) && (decPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Lang27
### Patch Diff Hash-SHA-256:

dcb40cb16180c36a977df4241a75f80ade21371dac5cf6885875c4e2627ec772

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'O') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Lang27
### Patch Diff Hash-SHA-256:

d8f91a559585699685455b058994a3d06942b0a6ad079c8ffc9e56c97821194a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'A') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Lang27
### Patch Diff Hash-SHA-256:

692ea608f2d6d93584450316c87bd9ce523e321205a8c4d78c21cc65f267f795

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 25) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Lang27
### Patch Diff Hash-SHA-256:

eefc17e00e66571cc7f8f5f5c23affc391160e0a0226dedc0a5d493503710aeb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos < decPos) && (expPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Lang27
### Patch Diff Hash-SHA-256:

cbc04cc8113fc16cfc44a57fbdbbdeac839d3b4ddbe6ea5eaaef8869471da8cc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar >= 55296) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Lang27
### Patch Diff Hash-SHA-256:

72a1f246c80c63131118100bd40c231cfda6f76860200a57585ba7c966e97c35

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > ((expPos - decPos) / 2)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Lang27
### Patch Diff Hash-SHA-256:

2b503c1ea5d35a01c4981706704b0a7c74f257474c9e486c693ac9bf1b349223

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 55296) && (lastChar <= 56191)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Lang27
### Patch Diff Hash-SHA-256:

89e3d3427f18dde5856bef5d46ab053762f329f04e6ea654b3dfc8d4347fc66e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((lastChar == 'y') || (lastChar == 'Y')) && ((lastChar == 'e') || (lastChar == 'E'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Lang27
### Patch Diff Hash-SHA-256:

55e99423eb0caf85feb634ff5e8e418de5abb6c41d3f27a60348f45ec85f3114

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((INTEGER_MINUS_ONE) != null) && (INTEGER_MINUS_ONE.equals(SHORT_ZERO))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3f225d3c17a0c015145b788b6aa4bb6eb35dba014cf578f4c7550fe145c9c05

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 15) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Lang27
### Patch Diff Hash-SHA-256:

d7b09200ebc4f1c39c0e2452778f700ed75e471b77ca1255c4c8c4c0f2a49fa1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos >= 0) && (expPos >= 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Lang27
### Patch Diff Hash-SHA-256:

9e60ab46cbe711dc5494746dd314661d44f0910ba1132dfd9a46683428985da3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos != (-1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Lang27
### Patch Diff Hash-SHA-256:

025dff18ca44b97e35249d5b5630ec3718eddb7eab89efade50fcda61f49109c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Lang27
### Patch Diff Hash-SHA-256:

0cc775dd6b068f9e493500d8a984d007883e585bc5d4190b81ad18aa2c1e5fea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 127) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Lang27
### Patch Diff Hash-SHA-256:

c35e0c38d8445666cbb0d4aced6851094db021291342e36aa69551b77af0f7ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'x') || (lastChar == 'X')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Lang27
### Patch Diff Hash-SHA-256:

23f77928f2acc693f3b3dee3283ee355a28e4667686d61f3de5def830769da7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 65535) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Lang27
### Patch Diff Hash-SHA-256:

9cdc80c43a89a7c3122132a45bc39fbcbbf848fe20873f7bf3d5677bc6c2acde

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Lang27
### Patch Diff Hash-SHA-256:

477f5ed3842030133162f27c04010ee29418b768b1a83c15d77413e3da4c2942

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos >= 12) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Lang27
### Patch Diff Hash-SHA-256:

2f3fe67d236d2ba21595604947b8df5e98da91ba470d711dd07d2c558d0b9e5d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar != lastChar) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Lang27
### Patch Diff Hash-SHA-256:

d6509e79c31bab4d4247c7b630979ddbaacb0231df811bb2016929072963c8e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Lang27
### Patch Diff Hash-SHA-256:

132eec1c21c8f1075b5cdc53c7a7a3a513f4e02ee3f0fa86abb549de9b0271b2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos != expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Lang27
### Patch Diff Hash-SHA-256:

61fc3adbf21fc29add0af5005d63ac222999234373631de2d376691cdc207413

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (org.apache.commons.lang3.StringUtils.isEmpty(str)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Lang27
### Patch Diff Hash-SHA-256:

03ec1b5f1d9fce573b760c2683cc507da1c2022a23bbc4c36b6ab45d6acaf320

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((java.lang.Character.toUpperCase(lastChar)) != (java.lang.Character.toUpperCase(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Lang27
### Patch Diff Hash-SHA-256:

a7282aea96145eff066bb60e87322f69b510c43e773e6ed873a12602038f7122

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar >= 56320) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Lang27
### Patch Diff Hash-SHA-256:

1fff1365ecec2a2645a8b5b4e1a2d2855a6d906ec2dd8c4c6a3788d550e14ebe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos & 1) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Lang27
### Patch Diff Hash-SHA-256:

55605c8cd0609d3b45f163530e501ae940b825d609ad66c66ce658303e83ad37

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Lang27
### Patch Diff Hash-SHA-256:

9db53ba1c7ec75ff09d96bb322176521207963e0b98d5834d2a6474de6e01ce9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar > lastChar) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Lang27
### Patch Diff Hash-SHA-256:

44ce1f36d0d3fe8a7fcaf533ae4ffd7090b0c93f1f4bcddb4b71afce2b94f405

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) && ((lastChar == 'l') || (lastChar == 'L'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Lang27
### Patch Diff Hash-SHA-256:

6d1c8c7bde15503800b4734915f573c4e4f6cf9859eb5f33235591c4938cb2b6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == '_') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Lang27
### Patch Diff Hash-SHA-256:

d2d2c232372f2e4bfa1bb6a0a0fc42ed477da5430f53d4f16afe474ef5b113e5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos < expPos) && (decPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Lang27
### Patch Diff Hash-SHA-256:

51f037ce1a768e47a2be6416b29de21542e03ae2fc7a33f61b858309208c5466

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((DOUBLE_ZERO) == null) || ((LONG_ZERO) == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Lang27
### Patch Diff Hash-SHA-256:

6316b88db8ac1a5f2487c159901ccd98c9e2249c810d9fefef49f50a9ecacd21

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'n') || (lastChar == 'N')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Lang27
### Patch Diff Hash-SHA-256:

24b7e3b8d7a8335f1ff615b9de342d24e902d29c356abc905ea4f84616be32ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 4095) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Lang27
### Patch Diff Hash-SHA-256:

ddaa204b870d162afdbff21f94e5f4e0c7340733c1d94564b758e85a42f0430b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Lang27
### Patch Diff Hash-SHA-256:

a39aa62da9063dd6d05b33f5046574b0935f68a5516b24df70e4abd044827844

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar > 'z') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Lang27
### Patch Diff Hash-SHA-256:

1d75ce4cb90919343837dccbc9e1e820318055d1a187597d17a31ccf1d02bb14

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (DOUBLE_ZERO.isInfinite()) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Lang27
### Patch Diff Hash-SHA-256:

3cf8e1d797173643965a14dc451677dea68d2f0554b0c72acdc62cd4d7690674

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar < 16) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Lang27
### Patch Diff Hash-SHA-256:

e27bd119b442e75587d12de5724e32c6ea903a75f35464005e3ab75ca560e4bd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Lang27
### Patch Diff Hash-SHA-256:

342b70b1f2c2b2d9e52fc5a13496ccb5fab3596734b6213009292caf748e5f15

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (LONG_MINUS_ONE.getClass().getName().equals(INTEGER_ZERO.getClass().getName())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Lang27
### Patch Diff Hash-SHA-256:

8c86782505817a3f986b199e6853d79d6278b1521a27b77ccd30227960d459c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Lang27
### Patch Diff Hash-SHA-256:

5410ce01ce875fbfef62ed0634f995d487530b691114133caa6f5b241535ce3c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.charAt(((str.length()) - 1))) == ';') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Lang27
### Patch Diff Hash-SHA-256:

a1757b7584ea90c67272e7fa22c00c3a35faacafc0383ca0b58f72ee96df820f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos + 1) < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3a0e31ce78997b546a9bb3833c30626e01f2f230ce51540702134b9b59e331e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < decPos) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Lang27
### Patch Diff Hash-SHA-256:

da6b19efb1eb0295049368acee3eca330d9378da425409ce8cc596b8f2770412

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos != expPos) && (decPos >= 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Lang27
### Patch Diff Hash-SHA-256:

a292b1b992a25abc29c6b33091a3d25b22efd41f59ddd32b57a5638c09182fc5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.charAt((decPos + 1))) == '\'') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Lang27
### Patch Diff Hash-SHA-256:

940832785c4dd228283253d0b4fc5773995dec46fe689643efab69d4425154d5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((LONG_ZERO) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Lang27
### Patch Diff Hash-SHA-256:

7f5b7277cfa54e891061bfc4d4f9225240804aab1c673d7df4d6354f85da73ec

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos != decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Lang27
### Patch Diff Hash-SHA-256:

a0f4377a21b7d20021a4d5740d028383b4e1c7d4202ee832c5e0e05f4d5510dd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((INTEGER_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Lang27
### Patch Diff Hash-SHA-256:

b6158c01dacd1a0b3d3b2547bd940dd45c572ee27b38cbaa115efef7635a2c05

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((SHORT_MINUS_ONE) != null) && (SHORT_MINUS_ONE.equals(SHORT_ZERO))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Lang27
### Patch Diff Hash-SHA-256:

e9f05dc0911687ce0b07b6b81aa1b23fa7d3957d6bb538b92d2f7ad91c328234

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Lang27
### Patch Diff Hash-SHA-256:

7ad1b1b1730485ef41cc706be9351b200f608fd42d87e79da576cc442fea5219

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((decPos & 1) == 0) && ((decPos & 1) == 0)) && (decPos < 31)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Lang27
### Patch Diff Hash-SHA-256:

96b6fdebf2bc84851fd21ac7a0bddda3cc90985c6d43ade2a11aae51aeda5955

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'y') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Lang27
### Patch Diff Hash-SHA-256:

7f57839c71dd4a07fc13fcf065cfb26ad985775fb5fdd5bc6fb6bdd8c3d9ec96

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == 1) || (expPos == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Lang27
### Patch Diff Hash-SHA-256:

01025bb181f149dd7d4adfc6e3eedff24eb8a94987cba501d3e69cbb838e4989

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--expPos) >= 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Lang27
### Patch Diff Hash-SHA-256:

3a84b26c7116b0e8a2a7a22e022906873158635a0bb4d6c1a065045ac1215b2e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'n') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Lang27
### Patch Diff Hash-SHA-256:

083861f4f53f3d089c67924516d4970588c25d5d8728f1dae3e2f780f6ffbdc4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 's') || (lastChar == 'S')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Lang27
### Patch Diff Hash-SHA-256:

3df9524dba7e4665b5bdd4f06271d2f7b07e95437ee90ef766f429052cae1610

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos % 2) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Lang27
### Patch Diff Hash-SHA-256:

d89ed0291a30447e1c769954849b1433706e9ff3ab82e16211f97c02c3551853

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'N') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Lang27
### Patch Diff Hash-SHA-256:

2d86a19ef8dd95c849d0bf86bbf1b1167bdd91a1f082b1a3bf3b34d62327ca56

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Lang27
### Patch Diff Hash-SHA-256:

d677c614cf1540a06c011d8a5c54827684169ae771c04e5a10cfab5e97852b55

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || (org.apache.commons.lang3.StringUtils.isEmpty(str))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Lang27
### Patch Diff Hash-SHA-256:

895cfc5e3168ca1b46011ae7527dce9e009b485f7f1c280f71254b65ff7eb67a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'x') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Lang27
### Patch Diff Hash-SHA-256:

b44d7312ae06bdc68c2f95981f3294865ceaa1ff3ce78777b9ca22f296124511

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < expPos) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Lang27
### Patch Diff Hash-SHA-256:

889b0ac4b99d738d25d052001ecfff9eb202decb919ba40fc37fd156e03d8517

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.BooleanUtils.toBooleanObject(str)) == (java.lang.Boolean.TRUE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Lang27
### Patch Diff Hash-SHA-256:

85d30fcd4049771ec734cb17ecc66bbed2af5bfb9e47b3afe8c7f3be393bcd03

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 't') || (lastChar == 'T')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Lang27
### Patch Diff Hash-SHA-256:

59867b258bf7300b23fe2a99e60b83ff916c187408df704f8125acf162317534

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) || (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Lang27
### Patch Diff Hash-SHA-256:

96792d979569f953d6ed9f3c2b42edcfbcd39d17311de3fad4ebb0e362d723b7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) >= 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Lang27
### Patch Diff Hash-SHA-256:

df6ab7897d7c1746cb8a3f64a55513aec8aa10433b1ba9b3f451f4cedd4067de

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((INTEGER_ZERO) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Lang27
### Patch Diff Hash-SHA-256:

169b89350ebd3702c9dfc0fa30efe8f6d18776fa883933c2baec275654c4e66e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.regionMatches(true, expPos, str, 0, str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Lang27
### Patch Diff Hash-SHA-256:

d527fb30e99c465c8a14f3d1530c801b094b0c67f629ab502af5ae8c47a0b6f1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) != (str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Lang27
### Patch Diff Hash-SHA-256:

2415cc915d052d588b1f09c40ebf4bc2190d989ed7e17a54742ab45e6a81bc41

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > (java.util.Calendar.SATURDAY)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Lang27
### Patch Diff Hash-SHA-256:

3035e75e84ac843dea3262cd78279223e6c6fbd58b4b7e182efca8671227f3b7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Lang27
### Patch Diff Hash-SHA-256:

09173a99b04cb2c8f92a045a6ab2cfaa3272944a34fddbb6a63f92fd9e06d4fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) || ((str.length()) == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Lang27
### Patch Diff Hash-SHA-256:

b0d4fbed55f7409f00e3b6d92ff6fa967fcf911b4776914d5c5ca019845c80d0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar != lastChar) && ((java.lang.Character.toUpperCase(lastChar)) != (java.lang.Character.toUpperCase(lastChar)))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Lang27
### Patch Diff Hash-SHA-256:

4fda0526bb9b1a7152fcff89edeb35e3394ce2b09a57a76fe01e99f6c3c607ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 't') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Lang27
### Patch Diff Hash-SHA-256:

d5278af27b19cfea21164fc867072896bda6f5d4fa3341841ef58d491cff0a3f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) && (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Lang27
### Patch Diff Hash-SHA-256:

f09815424f9fd830c038f1a778d99b2f7c3e48a1ebdfc3c73bc5bc6fa187c730

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (java.lang.Character.UPPERCASE_LETTER)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Lang27
### Patch Diff Hash-SHA-256:

ee44c93c5f4b363e0d237e269e22ae256c8566c47cb0789f6843e80eeb48071d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'F') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Lang27
### Patch Diff Hash-SHA-256:

7765db9a9fb2595823c24fd69fbe630194bfefd7693d57596e5216449d173133

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Lang27
### Patch Diff Hash-SHA-256:

ce61ff3330d8d9b86872da669dac99d33a0ba89aafafe8e4c4ae3da04147bc5f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 7) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Lang27
### Patch Diff Hash-SHA-256:

4898ef3ffae4b0dbd5012c9c4a6f8fa140f0e8953ae5a9c8dadc7ee2cf3ef190

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) > (str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Lang27
### Patch Diff Hash-SHA-256:

5767fb700c996b2269d64808ec76107643dfdb4966f24a94504f0e92a401b057

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos + 1) < expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Lang27
### Patch Diff Hash-SHA-256:

2af0ccfedd4c9a73d304d15b9ca373f5c65845e48dbb118cf4b3611c699b8e71

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 's') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Lang27
### Patch Diff Hash-SHA-256:

53fe5b652d0a3194797ea947e410ec3aee1b04ec733841db4b99726af97c2c75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.regionMatches(true, expPos, str, 0, expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Lang27
### Patch Diff Hash-SHA-256:

20068e1f68ab9fd904e2656534871e404f541e1c9f20cb2346d412a78164a9d6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (java.lang.Integer.MIN_VALUE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3680beff78fe09ff3eca489d4fcaa0b723692057568a860830589845cd20d3a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.getClass()) != (str.getClass())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Lang27
### Patch Diff Hash-SHA-256:

7bbf990770c8f81bf04bd66be526e1a3f246d102ebd2597e8536512b2c22adb1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'o') || (lastChar == 'O')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Lang27
### Patch Diff Hash-SHA-256:

c1399531dad8c54a10353ce32f8d21e09afd2893705696a2a49d23d0f44affc6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (org.apache.commons.lang3.time.DateUtils.SEMI_MONTH)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Lang27
### Patch Diff Hash-SHA-256:

002945bb47495c6dbae8b78e0e5efab3834cf8a189c0da38d5fc940638d49d47

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (java.lang.Boolean.FALSE) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Lang27
### Patch Diff Hash-SHA-256:

8056264de216202a15ae3bc7cb0e475746fc7ed8347b11851313363668e72258

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Lang27
### Patch Diff Hash-SHA-256:

03d4d6bd58b4fb407d155b083258784a82b7ca8acd0596d2e0cc624e72b64e8c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'f') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Lang27
### Patch Diff Hash-SHA-256:

fa612d822e7806d3d9cbb7a37962094b5d5ba5c419403242493fd616ab0fbcc8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || ((str.indexOf(lastChar)) == (org.apache.commons.lang3.StringUtils.INDEX_NOT_FOUND))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Lang27
### Patch Diff Hash-SHA-256:

dfa6b76e2bb47994043e105f7b9bcf65e662d70f1ada95a05e6e94c3d64c0b15

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 'y') || (lastChar == 'Y')) && ((lastChar == 'e') || (lastChar == 'E'))) && ((lastChar == 's') || (lastChar == 'S'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Lang27
### Patch Diff Hash-SHA-256:

3b2ebe75b06b69072c8bde080061b1f4fc3963a04a6de18dcabf30cc6b744fe9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'U') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Lang27
### Patch Diff Hash-SHA-256:

653fdbe233ed83018468b7ec2f42c66231e76b7dbcd03476800d15acd6af9efc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < expPos) && ((str.charAt((expPos + 1))) == '\'')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Lang27
### Patch Diff Hash-SHA-256:

3640973fee14c22215c63b2414e286457dc76112ede44a6c48fb31dd889d6c01

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.startsWith("L")) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Lang27
### Patch Diff Hash-SHA-256:

8968adcdbde038a7859881e5d2b270184cce021750036c8cd9c9a1dadb1c1724

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'e') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Lang27
### Patch Diff Hash-SHA-256:

bb328c1099637a0c733839f1a2ad2184776938625d1babbae44253836d11d196

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.indexOf(lastChar)) < 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Lang27
### Patch Diff Hash-SHA-256:

7591dfe4703c5da016138516e5bf53a5f94fbfddfef97ba8fcfca8dddbdef6af

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (-1)) && (expPos != expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Lang27
### Patch Diff Hash-SHA-256:

6a4fd200d45ec7f49a275fd771c6aebb34ba4147c5a86a2124d4484ddb48bda2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (java.lang.Integer.MIN_VALUE)) && ((expPos & 1) == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Lang27
### Patch Diff Hash-SHA-256:

5c44039e1f831a2ad1301d26fc303382fcf33f1e343a5cb578ac860103d2957a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'y') || (lastChar == 'Y')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Lang27
### Patch Diff Hash-SHA-256:

9d55585ab049d15e6b2f58f254ce108470175c9a6dd95d7953c4ef4fc50f7df5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--expPos) >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Lang27
### Patch Diff Hash-SHA-256:

0e2e22331d67259b853bb0368020736fae8647a75504d6dc32ef973f5aeccd66

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring(1);
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Lang27
### Patch Diff Hash-SHA-256:

a33b11911b21bd09963e3399684f17ca58a0d3f8cc9108de71ab56515b2fd5c6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1), str.length());
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Lang27
### Patch Diff Hash-SHA-256:

2ef9796d9e12b0e9965ccb662f368a76f2842baabf6656ce0ef86e7676df04cb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -152,7 +152,7 @@
 		java.lang.String dec;
 		java.lang.String exp;
 		int decPos = str.indexOf('.');
-		int expPos = ((str.indexOf('e')) + (str.indexOf('E'))) + 1;
+		int expPos = (str.indexOf('e')) + (str.indexOf('E'));
 		if (decPos > (-1)) {
 			if (expPos > (-1)) {
 				if (expPos < decPos) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Lang27
### Patch Diff Hash-SHA-256:

3bdb5afca5df5e375fe88f806af652129c39bec32c82a7000b1243725c7e09bf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring(0, ((str.length()) - 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Lang27
### Patch Diff Hash-SHA-256:

fa0552fe6b78e09c8609676ccb9bea70a6ee710fbcd4137a9623bba896428ca2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1), ((str.length()) - 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Lang27
### Patch Diff Hash-SHA-256:

f17193c0db20d941bdc5e05c3f3058418275ab78e9b3b230cfc3ba1e1c27f640

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Lang27
### Patch Diff Hash-SHA-256:

6c6e6fc948b90e648817f65aa4994640b49a9b08d173332b36ab782364598360

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((str == null) && (str == null)) && ((((str.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(str.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(str)))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Lang27
### Patch Diff Hash-SHA-256:

fdfa343a2bec1cd4fb481ed5dcc5d5a8d8362908c0bb12719013c80ec4e752f5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos > (-1)) && (decPos < ((str.length()) - 1))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---