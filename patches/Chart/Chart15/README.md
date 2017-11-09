
# Patches of Chart15 from Defects4J 
Total patches 24
## Patch 1 of bug id Chart15
### Patch Diff Hash-SHA-256:

984f844de4c73b4353cdbc55ac9c781b8cd2a967da3b1173eecdcfadc84ba3d2

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		setNotify(false);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart15
### Patch Diff Hash-SHA-256:

123d078d90e09e7d0eb1b3f92584e683ca120a0de708e67a27665bc420885b52

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		subtitles.clear();
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart15
### Patch Diff Hash-SHA-256:

7e2b760f4fb85b342bb516c7c66b9424db77fbe2117901747cead5710569d95b

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.addRenderingHints(renderingHints);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart15
### Patch Diff Hash-SHA-256:

e90d9fcd1b47a8c853cace28225709cc926381b1cb1bb1d05417b9d0de5f4df1

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		fireChartChanged();
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart15
### Patch Diff Hash-SHA-256:

f232f17440cd049937d8d5e6532573a068442ea46e9e2ab1b5b80f2b834c78de

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart15
### Patch Diff Hash-SHA-256:

54ab66044c45d58d8a57e8d71a253a5b23cba43c7f952967cd1f51279699fc44

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		removeSubtitle(getLegend());
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart15
### Patch Diff Hash-SHA-256:

b4cde82d4e669d5aeadadfd5feadce10a78ff066500725c8f43f8ce4a56ae23a

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.clip(chartArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart15
### Patch Diff Hash-SHA-256:

a9ada505c5d5f53394b043392ba80c8be2ccc1977899f0ac62bbd2607e3e983e

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_STARTED, 0));
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart15
### Patch Diff Hash-SHA-256:

ac2cde112c348a56cd16d10ab42d4beb5345305af46857fd2ec0286fbfd288ab

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		plot.addChangeListener(org.jfree.chart.JFreeChart.this);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart15
### Patch Diff Hash-SHA-256:

2611278f97dbc450ee7494cc494ac6e33126369b9e4e6c07e023b90e1b72f2f4

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.fill(chartArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart15
### Patch Diff Hash-SHA-256:

781281b83ef623cdacb11e6bae04ef330e91c4549385468f5e799f7149a2b984

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.draw(chartArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart15
### Patch Diff Hash-SHA-256:

1de15790e8a220c463b04516990321faf3587101f679963ad092e27fc8a7ff7e

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setPaint(backgroundPaint);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart15
### Patch Diff Hash-SHA-256:

c7f8ec85ba6decf2053dd2f309f5e35a8649b0ac783e5b1b3780038fe9e8af70

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		setNotify(true);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart15
### Patch Diff Hash-SHA-256:

edd67d3320ad018edeca525380ef4b804f659307c439982f8984d3a0d74f18f7

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		org.jfree.chart.util.Align.align(chartArea, chartArea, backgroundImageAlignment);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart15
### Patch Diff Hash-SHA-256:

39d44db160c6bad6b8047f78f05386d187ddf12faae656ac3fcd97a5003f6ac5

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		clearSubtitles();
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart15
### Patch Diff Hash-SHA-256:

ec1aa38bab6126e9ca3735f24d6f376f31628633aa043673d55cb110c7c2b9e6

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		notifyListeners(new org.jfree.chart.event.ChartChangeEvent(org.jfree.chart.JFreeChart.this));
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart15
### Patch Diff Hash-SHA-256:

77edb739a81b1818d8b896f9c25c27cf16b017d9eba40799877e52384a94d3b2

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setClip(chartArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart15
### Patch Diff Hash-SHA-256:

5d50b01e5e9b2b4c0e6805c66ec2e5275ae2b2bd2756ad537dc5604bcf84d672

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setClip(nonTitleArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart15
### Patch Diff Hash-SHA-256:

5ebe03940b21b883ce943e239d6486b5aad0cf3166dfceb1a0934c9a83320e63

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.draw(nonTitleArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart15
### Patch Diff Hash-SHA-256:

3ea01252454d4bc6574b0bf51c6aa42a103ab0d7ab088ad45d74d4912561a86d

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		padding.trim(nonTitleArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart15
### Patch Diff Hash-SHA-256:

56faefb47ecbd8ac097515fcf217986eb5290ab2c6039704daa7dc55392ab9e6

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		org.jfree.chart.util.Align.align(chartArea, nonTitleArea, backgroundImageAlignment);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart15
### Patch Diff Hash-SHA-256:

c5dd1c812e7cfc1066bb52620a3cf7e006cdf069a8aef3c5c471c764d4a88874

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.draw(plotArea);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart15
### Patch Diff Hash-SHA-256:

8968c0d68c1d37fe7a436305cda2b39ea2dd006ddfc17a37912e6df8c3a2a545

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		setTitle(((org.jfree.chart.title.TextTitle) (null)));
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart15
### Patch Diff Hash-SHA-256:

1a1b4c275678d321ad98062f8f34912c3713aeca2db9333de4252459412ce9e3

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setClip(savedClip);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -733,31 +731,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---