E0 – Exercise preparation:<br />Create a new project in Eclipse that will be the root of your exercise directories<br />Create a new Eclipse project using the Mail template. Place it as a children folder of the exercise root directory<br />Create a new plugin with some content (e.g. one class) in the same location<br />Modify the Mail application plugin to depend on the newly created plugin and use some of the contents (e.g. the class)<br />E1 – Create pom.xml files for all the plugins. Then create a super pom.xml file on the exercise root directory including:<br />  Properties:<br />    tycho.version = 1.4.0<br />    java.version = JavaSE-11<br />  Tycho plugin<br />  Repository location:<br />E2 – Create a Target Platform useable for development and for Tycho build in a dedicated directory.<br />  Use the same URL used in E1 for finding the repositories<br />  Include features:<br />    org.eclipse.sdk.feature.group<br />    org.eclipse.emf.sdk.feature.group<br />    org.eclipse.equinox.executable.feature.group<br />  Remove the <repository> section from the parent pom.xml<br />  Create pom.xml for the Target Platform<br />  Configure parent pom.xml:<br />  Add the Target Platform to the list of modules<br />  Configure tycho target platform plugin
