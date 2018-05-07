
# Patches of Math7 from Defects4J 
Total patches 1
## Patch 1 of bug id Math7
### Patch Diff Hash-SHA-256:

beae7fe5596ec4e267f1d6dbe1acc4d7b21a023c8dba53fb375c67325e270fd0

### Patch Diff:
```
--- /original/org/apache/commons/math3/ode/AbstractIntegrator.java	
+++ /fixed/org/apache/commons/math3/ode/AbstractIntegrator.java	
@@ -45,6 +45,7 @@
 	}
 
 	public void addStepHandler(final org.apache.commons.math3.ode.sampling.StepHandler handler) {
+		eventsStates = new java.util.ArrayList<org.apache.commons.math3.ode.events.EventState>();
 		stepHandlers.add(handler);
 	}
```


---