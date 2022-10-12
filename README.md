# ManuallyCreatedMavenProject
Project created without Spring Initializr, only mvn 

################################
#Previously you need:          #
#     java and mvn installed   #
################################

1) Create repository
2) Clone empty repository
3) Open terminal and go to your repository, then build the following directory structure: src/java/main/simple
4) Then create your main class file (in this case HelloWorld.java)
5) Make it do anything you want to, and don't forget to code the public static void main(String[] args) method
6) Go to base directory of your recently built repo, next to src/ directory
7) Create a file called pom.xml and add the following content:
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.springframework</groupId>
    <artifactId>gs-maven</artifactId>
    <packaging>jar</packaging>
    <version>0.1.0</version>

    <properties>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
    </properties>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-shade-plugin</artifactId>
                <version>3.2.4</version>
                <executions>
                    <execution>
                        <phase>package</phase>
                        <goals>
                            <goal>shade</goal>
                        </goals>
                        <configuration>
                            <transformers>
                                <transformer
                                    implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
                                    <mainClass>simple.HelloWorld</mainClass>
                                </transformer>
                            </transformers>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>

8) Execute 'mvn compile', then 'mvn package'
9) Execute 'java -jar target/gs-maven-0.1.0.jar'
10) Develop as much as you want from here on ...
