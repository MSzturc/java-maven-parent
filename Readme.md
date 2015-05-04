java-maven-parent
====================

Parent POM for Java8 based projects. Provides default project build configuration.


Introduction
---------------------

The Java Maven parent POM provides default configuration for Java8 based Maven applications.

* Recommended/Default versions for the most commonly used Maven plugins
* Code coverage measure based on jacoco-maven-plugin
* Defect detection based on FindBugs / PMD
* Code conventions checking based on checkstyle
* Maven Profile to toggle code analysis


Usage
---------------------

Start out by adding the parent configuration to your pom.
	
    <parent>
        <groupId>de.mszturc</groupId>
        <artifactId>java-parent</artifactId>
        <version>1.0</version>
    </parent>

The pom includes properties which allow various build configuration to be 
customized.  For example, to override the default version of the
maven-compiler-plugin, just set a property.

    <properties>
      <maven.compiler.plugin.version>3.3</maven.compiler.plugin.version>
    </properties>

Or override the default Java compiler source and target level used in the build.  
Note the default level is 1.8.

    <properties>
      <project.build.sourceLevel>1.7</project.build.sourceLevel>
      <project.build.targetLevel>1.7</project.build.targetLevel>
    </properties>

	
The Code Analysis Profile
--------------------
The parent POM includes a Maven profile called "code-analysis".  This profile analyzes 
managed assemblies and reports information about the assemblies, such as violations 
of the programming and design rules. The analysis tool represents the checks it performs 
during an analysis as warning messages. Warning messages identify any relevant programming 
and design issues and, when it is possible, supply information about how to fix the problem.

To trigger a code analysis from the CLI use the following command:

    mvn -Pcode-analysis
	
	
Technical Notes
---------------------

For the creation of the project I used the following tools & plugins:

- Java JDK 1.8.0_25-b18 x64
- Maven 3.1.1

The project was test in the following environment:

- Windows 7 x64
- Java JDK 1.8.0_25-b18 x64
- Maven 3.1.1