# Maven

Apache Maven is a software project management and comprehension tool. A build automation tool that helps managing the software build lifecycle.

<b>Maven artifact</b>
An artifact is a JAR, that gets deployed to a Maven repository.

Each artifact has a group ID , an artifact ID (artifact name) and a version string.

<b>Types of maven repository.</b>
local.
central.
and remote.

<b>Build phases in Maven</b>
Validate.
Compile.
Test.
Package.
Install.
Deploy.

<b>Explain the highlevel directory structure of a maven project</b>
<b>target:</b> folder holds the compiled unit of code as part of the build process.

<b>Source:</b> folder usually src/main/java holds java source codes.

<b>Test:</b> directory is src/main/test that has all the unit testing codes.

<b>What jar:jar goal does?</b>
It creates the jar files from the target/classes directory without recompiling any source classes.

<b>What are the minimum requirements for a POM?</b>
The minimum requirement for a POM are the following,
project root
modelVersion
groupId
artifactId
version

<b>Can we use different name for POM.xml?</b>
Yes. You could mention file name using the -f option.
    mvn -f parent-pom.xml
    
<b>How do you rename a maven project?</b>
1) Rename the project using Eclipse or other IDE.

2) Update the artifactId in your pom.xml

<b>maven repository central</b>
It is the Maven established repository. For example, your POM specify the dependencies and it is not available in the configured local and the remote repository then maven looks for the resource in Maven Central. Maven provides most of the generic dependency resources at this remote location.

<b>POM</b>
POM (Project Object Model) is the fundamental unit of work. It is an XML file which holds the information about the project and configuration details used to build a project by Maven along with its dependencies.

<b>Maven Repository</b>
The location where all the project jars, library jars, plugins or any other project related artifacts that are stored and can be easily used by Maven.

<b>Why Maven is used?</b>
• Create a jar file
• Create war file
• Compile code
• Unit testing of code
• Documenting projects
• Reporting

<b>Where do we find .class files of a Maven project?</b>
Under the folder ${basedir}/target/classes/.

<b>Difference between compile and install.</b>
Compile compiles the source code of the project whereas Install installs the package into the local repository, for use as a dependency in other projects locally.

<b>What is a Maven project's fully qualified artifact name?</b>
<groupId>:<artifactId>:<version>

<b>Order by which Maven searches for the dependency.</b>
Local -> Remote -> Maven Central

<b>groupId</b>
Identifies a project uniquely across all projects.

<b>artifactId</b>
it becomes the name of the jar file.

<b>Explain the difference phases in Maven build Lifecycle.</b>
<b>validate</b> - validates the project is correct and all necessary information is available.

<b>compile</b> - compile the source code of the project.

<b>test</b> - tests the compiled source code using a suitable unit testing framework. These tests does not require the code to be packaged or deployed.

<b>package</b> - take the compiled code and package it to its distributable format, for example, JAR.

<b>verify</b> - runs any checks on results of integration tests to ensure desired quality criteria are met.

<b>install</b> - installs the package into the local repository, for using it as a dependency in other projects locally.

<b>deploy</b> - performed in the build environment, copies the final package to the remote repository for sharing and collaboration with other members of the team and projects.

<b> How do I specify packaging/distributable format in Maven?</b>
The packaging for your project can be specified via the POM element <packaging>.

Some of the valid packaging values are jar, war, ear and pom. If no packaging value has been specified, it will default to jar.

            <project xmlns="http://maven.apache.org/POM/4.0.0"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                                  http://maven.apache.org/xsd/maven-4.0.0.xsd">
              ...
              <packaging>war</packaging>
              ...
            </project>
            
 <b>How Maven searches for dependency JAR?</b>
 Maven searches first for a dependency JAR in local repository. If found it is used else maven looks st the remote repository and download the corresponding version of JAR file and then stores it into local repository.
