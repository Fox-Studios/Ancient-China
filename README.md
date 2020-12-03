# Ancient-China
A mod dedicated to creating a beautiful ancient Chinese scene


# setup
====== Setting up a mod development environment ======

===== Prerequisites =====

   * A Java Development Kit (JDK) for Java 8 (recommended) or newer [[https://adoptopenjdk.net/]]
   * Any Java IDE, for example [[https://www.jetbrains.com/idea/download/#section=windows|Intellij IDEA]] and [[https://www.eclipse.org/downloads/|Eclipse]]. You may also use any other code editors, such as [[https://code.visualstudio.com/|Visual Studio Code]].

=== IntelliJ IDEA ===
If you are using IntelliJ IDEA by JetBrains, please follow these steps:
    - In the IDEA main menu, select 'Import Project' (or File -> Open... if you already have a project open).
    - Select the project's build.gradle file to import the project.
    - After Gradle is done setting up, close (File -> Close Project) and re-open the project to fix run configurations not displaying correctly.
    - (If the run configurations still don't show up, try reimporting the Gradle project from the Gradle tab in IDEA.)

//Optional, but recommended//:
By default, IntelliJ delegates to Gradle to build the project. This is unnecessary for Fabric and causes longer build times and hotswapping related weirdness, among other problems. To make it use the builtin compiler:
    - Open the 'Gradle Settings' dialog from the Gradle tab.
    - Change the 'Build and run using' and 'Run tests using' fields to 'IntelliJ IDEA'.
    - Go to File -> Project Structure -> Project and set 'Project compiler output' to ''$PROJECT_DIR$/out''.

Unfortunately, it is currently impossible to set an IDE-wide default for the 'Build and run using' and 'Run tests using' options, so these steps have to be repeated for every new project.

**NOTE:** Don't run ''./gradlew idea'' as it messes up with gradle and breaks develop environment.

=== Eclipse ===
If you are using Eclipse and you would like to have the IDE run configs you can run ''gradlew eclipse''.

=== Visual Studio Code ===
If you are using VSCode by Microsoft, please follow [[tutorial:vscode_setup|these instructions]]

==== MinecraftDev IntelliJ IDEA Plugin ====
If you are using IntelliJ IDEA you can use the MinecraftDev plugin. This plugin adds support for automatically generating Fabric projects as well as some mixin related features like inspections, generating accessors/shadow fields, and copying Mixin Target References (JVM Descriptors).
The plugin can be found [[https://plugins.jetbrains.com/plugin/8327|in the IntelliJ plugin repository]], so you can install it using IntelliJ's internal plugin browser by navigating to File → Settings → Plugins, then clicking the Marketplace tab and searching for Minecraft.

===== Troubleshooting =====

==== Missing sounds ====

Sometimes, when importing the Gradle project into an IDE, the assets might not download correctly. In this case, run the ''downloadAssets'' task manually - either using IDE's built-in menu or by simply running ''gradlew downloadAssets''.
