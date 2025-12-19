# Welcome to the Setup guide.
here we're going to get all the necessary tools build to help us build and modify our minecraft server more freely. then we're going to create the right environment for our modifications. **THIS TUTORIAL IS MADE WITH THE ASSUMPTION THAT JAVA IS ALREADY INSTALLED**

List of downloads:

[**Paper**](https://papermc.io/downloads/paper) - Download Accroding to the server's version

[**Apache Maven**](https://maven.apache.org/download.cgi) - Download the binary zip version of the latest release

[**Visual Studio Code**](https://code.visualstudio.com)

## Step 1, creating the server:
Once downloaded the paper server host, move it to an empty folder with a memorable name. then, run the downloaded file by right clicking on a blank place in the tab whilst in the server, selecting "Open In Terminal", and typing or copying the following line:  
java -Xms2G -Xmx4G -jar SERVER.jar  
(Replace "SERVER" with your jar file name)  
This will create a server thet consumes between 2 and 4 gigabytes of RAM while running. The Program will stop in order for you to accept the eula. After Accepting run the same line again and your Paper server will be created. You can customise the server a bit by going to the properties file "server.properties" or leave it as a default server. in order to join the game, go into your multiplayer section in minecraft and enter your ip, which can be accessed in the wifi settings **(DO NOT SHARE YOUR IP WITH UNTRUSTWORTHY INDIVIDUALS)**  
Now You got your very own functioning private paper Server
## Step 2, adding the compiler Maven:
Maven is a software we would use in this series in order to compile your code into a plugin the erver could understand.  
After downloading the compiler, we need the computer to recognize it. we would do it by first extracting the maven file and moving it the extracted folder to a source folder (selecting the folder that is acting as a source is your choice). now go into the environment variables settings and configure it so it would include maven.  
In Windows: search environment variables in start and select the first option. Then, click "Environment Variables..." assuming that you're under the "Advanced" tab. under "System variables" click on the "Path" Variable twice to access it. Afterwards, click new and copy the folder path of the bin directory of your maven file.  
Example: C:\Users\USER\SOURCE\MAVEN\bin.  
"USER" being the username of the current profile, "SOURCE" being the folder or folders containing the maven folder and "MAVEN" being the maven file. The easiest way to do so would be to go to your maven folder, going to bin, and then copying the file path from the search bar in the file explorer. After, Conferming your Settings. the mvn compiler is recognized.  
## Step 3, installing the coding environment:  
in this series, we're going to use VIsual Studio Code as the environment used to develo the plugins.  
install the downloaded Visual Studio Code exe file. after that, fo to the extensions tab on the sidebar of the editor and search for java. install the suggested extension by Oracle or Microsoft.
## Step 4, Creating the project:  
Now that everything's ready, all that is left is the project itself. start by returning to the explorer tab on VS Code. then, click "Open Folder", and choose/add your desired folder to work on. when selecting this folder add the file pom.xml and copy the following code:  
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
            xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
            xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://www.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>unique</groupId>
    <artifactId>uniquename</artifactId>
    <version>1.0.0-SNAPSHOT</version>
    <name>uniquename</name>
    <url>domain.com</url>
    <repositories>
        <repository>
            <id>spigot-repo</id>
            <url>https://hub.spigotmc.org/nexus/content/repositories/snapshots/</url>
        </repository>
        <repository>
            <id>paper-api</id>
            <url>https://repo.papermc.io/repository/maven-public/</url>
        </repository>
    </repositories>

    <dependencies>
        <dependency>
            <groupId>org.spigotmc</groupId>
            <artifactId>spigot-api</artifactId>
            <version>1.21.11-R0.1-SNAPSHOT</version>
            <scope>provided</scope>
        </dependency>
            <dependency>
            <groupId>io.papermc.paper</groupId>
            <artifactId>paper-api</artifactId>
            <version>1.21.11-R0.1-SNAPSHOT</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>net.kyori</groupId>
            <artifactId>adventure-text-minimessage</artifactId>
            <version>4.14.0</version>
            <scope>provided</scope>
        </dependency>
    </dependencies>

    <build>
        <sourceDirectory>${project.basedir}/src/main/java</sourceDirectory>
        <resources>
            <resource>
                <directory>${project.basedir}/src/main/resources</directory>
                <includes>
                    <include>plugin.yml</include>
                </includes>
            </resource>
        </resources>
    </build>
</project>
```

now create two folders next to it, "target" and "src".  
do not touch the "target" folder. under the "src" do the following steps:  
create folder "main",  
under main create the folders "java" and "resources"  
under "resources" create the file "plugin.yml" and paste the following code into it:  
```yml
main: project.Tutorial  
version: 1.0.0-SNAPSHOT  
name: tutorial-proj  
author: mycoolname  
api-version: 1.21  
description: this is a cool plugin!
```


and under "java" create the folder "project"  
under project create the folders "listeners", "managers", "utils" and the file "Tutorial.java"  
under "managers" create the file "PluginManager.java"  
under "listeners" create the file "PlayerListener.java"  
under "utils" create the file "Utils.java"  

in "Tutorial.java" paste the following code:  
```java
package project;
```
in "PluginManager.java" paste the following code:  
```java
package unique.managers;  
```
in "PlayerListener.java" paste the following code:  
```java
package unique.listeners;  
```
in "PlayerListener.java" paste the following code:  
```java
package unique.utils;
```

Congrats!
