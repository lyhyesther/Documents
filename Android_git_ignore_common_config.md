
<pre>
# 该符号为注释符号将被git忽略

# 忽略.gitignore文件
.gitignore

# 忽略所有.a后缀的文件
.a

# 忽略后缀为 .o 和.a的文件
*.[oa]

# 忽略 xx.a除外的文件
!xx.a

# 忽略指定名称为main的文件
main

# 忽略根目录下的main文件
/main

# 忽略指定文件夹
main/

# gitignore文件的目的是确保未被Git跟踪的某些文件保持未被跟踪。
# 如果项目已被纳入版本管理， 再修改.gitignore是无效的，
# 要停止跟踪当前跟踪的文件，请使用 git rm --cached，
# 把本地缓存删除后再提交


# Built application 文件
*.apk
*.ap_

# ART/Dalvik VM 文件
*.dex

# Java class 文件
*.class

# Generated 文件夹
bin/
gen/
out/

# Gradle files
.gradle/
build/

# 本地配置文件 (sdk path, etc)
local.properties

# Eclipse生成的Proguard文件夹
proguard/

# 日志文件
*.log

# Android Studio导航编辑器临时文件
.navigation/

# Android Studio captures folder
captures/

# IntelliJ (IDE配置文件)
*.iml
.idea/workspace.xml
.idea/tasks.xml
.idea/gradle.xml
.idea/assetWizardSettings.xml
.idea/dictionaries
.idea/libraries
.idea/caches

# 密钥储存库文件
# 如果您不想检查密钥库文件，请取消注释以下行
#*.jks

# 在Android Studio 2.2及更高版本中生成的外部原生构建文件夹
.externalNativeBuild

# Google服务 (e.g. APIs or Firebase)
google-services.json

# Freeline (Android 平台上的秒级编译方案)
freeline.py
freeline/
freeline_project_description.json

# fastlane (自动化打包框架)
fastlane/report.xml
fastlane/Preview.html
fastlane/screenshots
fastlane/test_output
fastlane/readme.md
</pre>
