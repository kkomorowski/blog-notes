---
icon: mug-hot
---

# Java Virtual Machine

## IllegalAccessException: module java.base does not open java.lang to unnamed module

### Cause

Starting with Java 9 and the module system, internal packages like `java.lang` are not open to all by default. When reflective access tries to access these restricted APIs (which often happens with older libraries or code expecting unrestricted access), this `IllegalAccessException` occurs.

### How to Fix

The solution is to explicitly open or export these packages to allow reflective access. This is done by adding JVM arguments that open the module/package to "ALL-UNNAMED" modules (which includes code not in any named module).

Add following option to JVM parameters for your application:

```
--add-opens java.base/java.lang=ALL-UNNAMED
```
