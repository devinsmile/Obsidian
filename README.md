Obsidian [![Build Status](https://travis-ci.org/ObsidianBox/Obsidian.png?branch=master)](https://travis-ci.org/ObsidianBox/Obsidian) [![Coverage Status](https://coveralls.io/repos/ObsidianBox/Obsidian/badge.png)](https://coveralls.io/r/ObsidianBox/Obsidian)
=============
Obsidian is a framework that extends Forge to deliver server-side content on demand. It is licensed under the [MIT License]

* [Homepage]
* [Source]
* [Issues]
* [Chat]: #obsidiandev on irc.esper.net

## Prerequisites
* [Java] 7
* [Gradle] 1.12+

## Cloning
If you are using Git, use this command to clone the project: `git clone git@github.com:ObsidianBox/Obsidian.git`

## Setup
__Note:__ If you do not have [Gradle] installed you can use the gradlew files included with the project in place of 'gradle' in the following command(s). If you are using Git Bash, Unix or OS X then use './gradlew'. If you are using Windows then use 'gradlew.bat'.

__For [Eclipse]__  
  1. Run `gradle cleanCache --refresh-dependencies` to pull in dependencies cleanly.  
  2. Run `gradle setupDecompWorkspace`  
  3. Make sure you have the Gradle plugin installed (Help > Eclipse Marketplace > Gradle Integration Plugin)  
  4. Import Obsidian as a Gradle project (File > Import)
  5. Select the root folder for Obsidian and click **Build Model**
  6. Check Obsidian when it finishes building and click **Finish**

__For [IntelliJ]__  
  1. Run `gradle cleanCache --refresh-dependencies` to pull in dependencies cleanly.  
  2. Run `gradle setupDecompWorkspace`  
  3. Make sure you have the Gradle plugin enabled (File > Settings > Plugins).  
  4. Click File > Import Module and select the **build.gradle** file for Obsidian.

## Running
__Note 1:__ The following is aimed to help you setup run configurations for Eclipse and IntelliJ, if you do not want to be able to run Obsidian directly from your IDE then you can skip this.
__Note 2:__ When running the Server, make sure you set it to *__online-mode=false__* in the server.properties in ~/run/server!

__For [Eclipse]__  
  1. Go to **Run > Run Configurations**.  
  2. Right-click **Java Application** and select **New**.  
  3. Set the current project.  
  4. Set the name as `Obsidian (Client)` and apply the information for Client below.
  5. Repeat step 1 through 4, then set the name as `Obsidian (Server)` and apply the information for Server below.

__For [IntelliJ]__  
  1. Go to **Run > Edit Configurations**.  
  2. Click the green + button and select **Application**.  
  3. Set the name as `Obsidian (Client)` and apply the information for Client below.
  4. Repeat step 2 and set the name as `Obsidian (Server)` and apply the information for Server below.

__Client__

|     Property      | Value                                                                                                   |
|:-----------------:|:--------------------------------------------------------------------------------------------------------|
|    Main class     | net.minecraft.launchwrapper.Launch                                                                      |
|    VM options     | -Xmx1G -Xms512M -Dfml.ignoreInvalidMinecraftCertificates=true -Djava.library.path="../../build/natives" |
|   Program args    | --version 1.7.2 --tweakClass cpw.mods.fml.common.launcher.FMLTweaker --accessToken Obsidian             |
| Working directory | ~/run/client (Included in project)                                                                      |
| Module classpath  | Obsidian (IntelliJ Only)                                                                                |

__Server__

|     Property      | Value                                                         |
|:-----------------:|:--------------------------------------------------------------|
|    Main class     | cpw.mods.fml.relauncher.ServerLaunchWrapper                   |
|    VM options     | -Xmx1G -Xms512M -Dfml.ignoreInvalidMinecraftCertificates=true |
| Working directory | ~/run/server (Included in project)                            |
| Module classpath  | Obsidian (IntelliJ Only)                                      |


## Building
__Note:__ If you do not have [Gradle] installed you can use the gradlew files included with the project in place of 'gradle' in the following command(s). If you are using Git Bash, Unix or OS X then use './gradlew'. If you are using Windows then use 'gradlew.bat'.

In order to build Obsidian you simply need to run the `gradle` command. You can find the compiled JAR files in `~/build/distribution` but in most cases you'll only need 'obsidian-x.x.x-SNAPSHOT.jar'.

## Contributing
Are you a talented programmer looking to contribute some code? We'd love the help!
* Open a pull request with your changes, following our [guidelines and coding standards](https://github.com/ObsidianBox/Obsidian/wiki/Contributing).
* Please follow the above guidelines and requirements for your pull request(s) to be accepted.
* For help setting up the project, keep reading!  

Love the project? Feel free to [donate] to help continue development! Obsidian is open-source and powered by community members, like yourself. Without you, we wouldn't be here today!

## FAQ
__Why do I get `javac: source release 1.7 requires target release 1.7` in IntelliJ when running the client configuration?__
>Sometimes another project can mess with the settings in IntelliJ. Fixing this is relatively easy.

>1. Go to 'File > Settings'.
>2. Click the drop down for 'Compiler' on the left-hand side and select 'Java Compiler'.
>3. Select Obsidian and set the 'Target bytecode version' as '1.7'.
>4. Click Apply and OK and try running it again.

__Why do I get `Zip file rt.jar failed to read properly` in IntelliJ?__
>This is the result of Forge attempting to classload the Java runtime JAR, overall it is not an error that will cause any harm to your development and should be ignored.

__A dependency was added, but my IDE is missing it! How do I add it?__
>If a new dependency was added, you can just restart your IDE and the Gradle plugin for that IDE should pull in the new dependencies.

__Help! Things are not working!__
>Some issues can be resolved by deleting the '.gradle' folder in your user directory and running through the setup steps again. Otherwise if you are having trouble with something that the README does not cover, feel free to join our IRC channel and ask for assistance.

[Chat]: http://obsidianbox.org/chat/
[Donate]: http://obsidianbox.org/donate/
[Eclipse]: http://www.eclipse.org/
[Gradle]: http://www.gradle.org/
[Homepage]: http://obsidianbox.org/
[IntelliJ]: http://www.jetbrains.com/idea/
[Issues]: http://obsidianbox.org/issues/
[Java]: http://java.oracle.com/
[Source]: https://github.com/ObsidianBox/Obsidian/
[MIT License]: http://www.tldrlegal.com/license/mit-license/
