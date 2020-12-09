![Logo](./Logo.png)
# Ancient-China
一个致力于创造美丽的中国古代场景的mod

A mod dedicated to creating a beautiful ancient Chinese scene


# setup
## 前置
* **JDK**（即用于开发Java的工具，推荐使用由AdoptOpenJDK提供的Java 8及以上版本的JDK https://adoptopenjdk.net/）
* **任意IDE**（集成开发环境）：如IntelliJ IDEA和Eclipse，也可使用任何可编辑代码的文本编辑器，如Visual Studio Code。

## 步骤
1. 在`build.gradle`中加入任何需要的其他第三方库。（一般会在模组页面/代码库上给出方法）
2. 将`build.gradle`导入到你的IDE中（各IDE操作各有不同，具体见下）
3. 配置完成！祝武运昌隆（bushi

你也可以生成MC的源文件来作为参考（不过IDEA已经自带反编译功能，所以生成不生成都随意）： 运行Gradle任务`genSources`（生成源文件），如果你的IDE不集成Gradle支持的话则需要在控制台/终端/命令提示符中输入`gradlew genSources`（在Linux或macOS上则是`./gradlew genSources`）

### IntelliJ IDEA
如果你使用的是IntelliJ IDEA，请遵循以下步骤：（注：中文文本可能会因为IDEA或中文插件的版本不同而不同）

1. 在IDEA的主菜单里选择“打开或导入…（Import Project）”（如果已经打开了一个项目，选择位于顶端的“文件→打开…”）
2. 选择项目的`build.gradle`文件以导入项目
3. 在Gradle配置完成后（注：国内的Gradle Build速度可能非常慢，可能可以持续好几小时，一定要有耐心.gif），关闭并重新加载项目，否则有些运行配置可能无法正常显示。
4. （如果运行配置还没有出现，试试在Gradle页面里重新导入项目。）

可选，但推荐做的一件事： IDEA默认使用Gradle来构建你的项目，而这在Fabric是不必要的，而且它会导致构建时间变长以及热替换（hotswapping）相关的种种问题。以下是让IDEA使用默认编译器的步骤：

1. 在Gradle页面里打开“Gradle设置（Gradle Settings）”
2. 将“使用此工具构建和运行（Build and run using）”和“使用此工具运行测试（Run tests using）”选项改成“IntelliJ IDEA”。
3. 进入 文件（File）→ 项目结构…（Project Structure…）→ 项目（Project）然后将模块编译输出路径（Project compiler output）改成$PROJECT_DIR$/out。
不幸的是目前还不能给“使用此工具构建和运行”和“使用此工具运行测试”设置一个全IDE内的默认值，所以这些每创建一个新项目都得重复上述步骤。

注：千万不要运行`./gradlew idea`，因为它会与Gradle冲突并破坏整个开发环境。
#### MinecraftDev IntelliJ IDEA插件
IntelliJ IDEA用户可以使用MinecraftDev插件来自动生成Fabric模组项目。该插件还有其他与Mixin相关的功能如审视（inspections，即高亮不当用法）、生成访问器（accessors）及影子成员（shadow members），以及自动填出目标引用（target descriptors，即JVM的方法描述符）。 这个插件可以在IntelliJ的插件库中找到，所以你也可以通过位于文件（File）→设置（Settings）→插件（Plugins）的内部插件浏览器找到并安装这个插件，只需要在搜索框里搜索“Minecraft”，选择第一个结果安装即可。

### Eclipse
如果你使用的是Eclipse，并且想要生成IDE的运行设置，请运行`gradlew eclipse`。

### Visual Studio Code
如果你使用的是Visual Studio Code，请参照[这篇教程](https://fabricmc.net/wiki/zh_cn:tutorial:vscode_setup "zh_cn:tutorial:vscode_setup")。

##故障诊断

###缺少声音
有时当IDE在导入Gradle项目的时候有些游戏素材不会正常下载。如果遇到这种情况则要手动运行`downloadAssets`任务——既可以使用IDE的自带菜单也可以直接执行`gradlew downloadAssets`。