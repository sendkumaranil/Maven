# Maven

Apache Maven is a software project management and comprehension tool. A build automation tool that helps managing the software build lifecycle.

<ul><li><b>Maven artifact</b></li></ul>
    An artifact is a JAR, that gets deployed to a Maven repository.

    Each artifact has a group ID , an artifact ID (artifact name) and a version string.

<ul><li><b>Types of maven repository.</b></li></ul>
    local.
    central.
    and remote.

<ul><li><b>Build phases in Maven</b></li></ul>
    Validate.
    Compile.
    Test.
    Package.
    Install.
    Deploy.

<ul><li><b>Explain the highlevel directory structure of a maven project</b></li></ul>
    <b>target:</b> folder holds the compiled unit of code as part of the build process.

    <b>Source:</b> folder usually src/main/java holds java source codes.

    <b>Test:</b> directory is src/main/test that has all the unit testing codes.

<ul><li><b>What jar:jar goal does?</b></li></ul>
    It creates the jar files from the target/classes directory without recompiling any source classes.

<ul><li><b>What are the minimum requirements for a POM?</b></li></ul>
    The minimum requirement for a POM are the following,
    project root
    modelVersion
    groupId
    artifactId
    version

<ul><li><b>Can we use different name for POM.xml?</b></li></ul>
    Yes. You could mention file name using the -f option.
        mvn -f parent-pom.xml
    
<ul><li><b>How do you rename a maven project?</b></li></ul>
    1) Rename the project using Eclipse or other IDE.

    2) Update the artifactId in your pom.xml

<ul><li><b>maven repository central</b></li></ul>
    It is the Maven established repository. For example, your POM specify the dependencies and it is not available in the configured        local and the remote repository then maven looks for the resource in Maven Central. Maven provides most of the generic dependency        resources at this remote location.

<ul><li><b>POM</b></li></ul>
    POM (Project Object Model) is the fundamental unit of work. It is an XML file which holds the information about the project and configuration details used to build a project by Maven along with its dependencies.

<ul><li><b>Maven Repository</b></li></ul>
    The location where all the project jars, library jars, plugins or any other project related artifacts that are stored and can be easily used by Maven.

<ul><li><b>Why Maven is used?</b></li></ul>
    • Create a jar file
    • Create war file
    • Compile code
    • Unit testing of code
    • Documenting projects
    • Reporting

<ul><li><b>Where do we find .class files of a Maven project?</b></li></ul>
    Under the folder ${basedir}/target/classes/.

<ul><li><b>Difference between compile and install.</b></li></ul>
    Compile compiles the source code of the project whereas Install installs the package into the local repository, for use as a dependency in other projects locally.

<ul><li><b>What is a Maven project's fully qualified artifact name?</b></li></ul>
    <groupId>:<artifactId>:<version>

<ul><li><b>Order by which Maven searches for the dependency.</b></li></ul>
    Local -> Remote -> Maven Central

<ul><li><b>groupId</b></li></ul>
    Identifies a project uniquely across all projects.

<ul><li><b>artifactId</b></li></ul>
    it becomes the name of the jar file.

<ul><li><b>Explain the difference phases in Maven build Lifecycle.</b></li></ul>
    <b>validate</b> - validates the project is correct and all necessary information is available.

    <b>compile</b> - compile the source code of the project.

    <b>test</b> - tests the compiled source code using a suitable unit testing framework. These tests does not require the code to be packaged or deployed.

    <b>package</b> - take the compiled code and package it to its distributable format, for example, JAR.

    <b>verify</b> - runs any checks on results of integration tests to ensure desired quality criteria are met.

    <b>install</b> - installs the package into the local repository, for using it as a dependency in other projects locally.

    <b>deploy</b> - performed in the build environment, copies the final package to the remote repository for sharing and collaboration with other members of the team and projects.

<ul><li><b> How do I specify packaging/distributable format in Maven?</b></li></ul>
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
            
 <ul><li><b>How Maven searches for dependency JAR?</b></li></ul>
     Maven searches first for a dependency JAR in local repository. If found it is used else maven looks st the remote repository and        download the corresponding version of JAR file and then stores it into local repository.
 
 <ul><li><b>Explain package phase in Maven build lifecycle.</b></li><ul>
    package phase pulls the compiled code and package it to a distributable format, such as a JAR.
    The below is the command to package a maven project.

    mvn -package  
    
 <ul><li><b>What are the build lifecycles of Maven?</b><li></ul>
     There are 3 built-in build lifecycles.

    The default lifecycle handles your project deployment.
    the clean lifecycle handles project cleaning.
    the site lifecycle handles the creation of the project's site documentation.
    
 <ul><li><b>What is local repository in Maven?</b></li></ul>
    Maven local repository is located in your local system and is created by the maven when you run any maven command.

    By default, maven local repository is %USER_HOME%/.m2 directory.

    We can change the location of maven local repository by changing the settings.xml file. It is located in MAVEN_HOME/conf.
 
 <ul><li><b>What is Maven Central Repository?</b></li></ul>
     Maven central repository is located on the web created by the apache maven community.

    The path of central repository is: http://repo1.maven.org/maven2/.   
 
 <ul><li><b>Explain Maven remote repository</b></li></ul>
     Remote repositories refer to any other type of repository, accessed by a variety of protocols such as file:// and http://. These       repositories are set up by a third party to provide their artifacts for downloading.

    A "remote" repository may also be an internal repository set up on a file or HTTP server within an organization, used to share           private artifacts between development teams and for releases.
  
  <ul><li><b>How do I include dependencies in a jar using Maven?</b></li></ul>
      Using jar-with-dependencies as the descriptorRef of your assembly-plugin configuration, we can create a JAR along its                   dependencies.
      This built-in descriptor creates an assembly with the classifier jar-with-dependencies using the JAR archive format.
      Below is the subset of pom.xml that includes assembly-plugin configuration along with jar-with-dependencies descriptor.
                        <build>
                        <plugins>
                          <!-- other plugin configuration -->
                          <plugin>
                            <artifactId>maven-assembly-plugin</artifactId>
                            <executions>
                              <execution>
                                <phase>package</phase>
                                <goals>
                                  <goal>single</goal>
                                </goals>
                              </execution>
                            </executions>
                            <configuration>
                              <descriptorRefs>
                                <descriptorRef>jar-with-dependencies</descriptorRef>
                              </descriptorRefs>
                            </configuration>
                          </plugin>
                        </plugins>
                      </build>
                      
 <ul><li><b>Configuring resource directories in Maven.</b></li></ul>
        By default, Maven configures and lookup into the src/main/resources directory for your project resources.
        Also additional resources directories could be specified by adding the configuration to the project's Pom.xml.
                <project>
                 ...
                 <build>
                   ...
                  <resources>
                   <resource>
                    <directory>
                     src/proj_resources
                    </directory>
                   </resource>
                </resources>
                 ...
                 </build>
                 ...
                </project>
                
 <ul><li><b>Difference between repository and dependency in Maven.</b></li></ul>
        Repository is a collection of artifacts (eg: jars). You can think of it as a mere storage / cache of various artifacts.
        Dependency is a situation where your project dependent on another artifact to perform its task. (For example., compile, run,             unit test etc.)
                
<ul><li><b>What is an Archetype in Maven framework?</b></li></ul>
        Archetype is a Maven plugin that creates a project structure as per its template.
        The below is the command to create a new maven project based on an archetype.

            mvn archetype:generate
<ul><li><b>What is goal in Maven?</b></li></ul>
        A maven goal represents a specific task that contributes to the building and managing of a Maven project. It may be bound to             zero or more build phases.
        A goal that does not bound to any build phase could be executed outside of the build lifecycle by direct invocation.

 
