E0 – Exercise preparation:
Create a new project in Eclipse that will be the root of your exercise directories
Create a new Eclipse project using the Mail template. Place it as a children folder of the exercise root directory
Create a new plugin with some content (e.g. one class) in the same location
Modify the Mail application plugin to depend on the newly created plugin and use some of the contents (e.g. the class)
E1 – Create pom.xml files for all the plugins. Then create a super pom.xml file on the exercise root directory including:
  Properties:
    tycho.version = 1.4.0
    java.version = JavaSE-11
  Tycho plugin:
      <plugin>
       <groupId>org.eclipse.tycho</groupId>
       <artifactId>tycho-maven-plugin</artifactId>
       <version>${tycho.version}</version>
       <extensions>true</extensions>
      </plugin>
  Repository location:
     <repositories>
        <repository>
          <id>eclipse-2018-12</id>
          <url>https://download.eclipse.org/releases/2018-12</url>
          <layout>p2</layout>
        </repository>
      </repositories>
E2 – Create a Target Platform useable for development and for Tycho build in a dedicated directory.
  Use the same URL used in E1 for finding the repositories
  Include features:
    org.eclipse.sdk.feature.group
    org.eclipse.emf.sdk.feature.group
    org.eclipse.equinox.executable.feature.group
  Remove the <repository> section from the parent pom.xml
  Create pom.xml for the Target Platform
  Configure parent pom.xml:
  Add the Target Platform to the list of modules
  Configure tycho target platform plugin
      <plugin>
       <groupId>org.eclipse.tycho</groupId>
        <artifactId>target-platform-configuration</artifactId>
       <version>${tycho.version}</version>
       <configuration>
      ...
