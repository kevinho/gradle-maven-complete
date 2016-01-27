[English README](README.md)

# 介绍
这是一个将『使用 gradle 发布 maven 库』的插件方案集合，包含如下内容：

* localrepo：发布包到本地仓库
* bintrayaar：发布 aar 包到 bintray jcenter
* bintrayjar：发布 jar 包到 bintray jcenter
* sonatypearr：发布 aar 包到 sonatype mavenCentral

对应的 Android Studio module 演示如何使用。

这是本人[拥抱 Android Studio](http://kvh.io/tags/EmbraceAndroidStudio/) 系列文章第四篇 [embrace-android-studio: maven-deploy](http://kvh.io/2016/01/20/embrace-android-studio-maven-deploy/) 的副产物，旨在帮助开发者入门，快速把包上传到对应的仓库。


# localrepo

记得修改 `localrepo/gradle.properties` 文件内容, 特别是:

```
LOCAL_REPO_URL=file:///Users/your-user-name/Documents/Android/repo/
```

使用如下命令来 build 和上传

```
$ ./gradlew -p localrepo clean build uploadArchives --info
```

# bintrayaar | bintrayjar
修改 `bintrayaar/local.properties` 或者 `bintrayjar/local.properties`:

```
bintray.apikey=your-api-bintray-key
bintray.user=your-bintray-user
bintray.gpg.password=your-gpg-password
```

使用如下命令来 build 和上传

```
$ ./gradlew -p bintrayaar clean build bintrayUpload --info
```

# sonatypeaar

修改 `sonatypeaar/local.properties`

```
NEXUS_USERNAME=admin
NEXUS_PASSWORD=admin123
RELEASE_REPOSITORY_URL=http://192.168.99.100:8081/content/repositories/releases
SNAPSHOT_REPOSITORY_URL=http://192.168.99.100:8081/content/repositories/snapshots
```
使用如下命令来 build 和上传

```
$ ./gradlew -p sonatypeaar clean build uploadArchives --info
```

# 鸣谢
感谢下面的大神和组织，我是从他们的项目中吸取了插件。

* [chrisbanes/gradle-mvn-push](https://github.com/chrisbanes/gradle-mvn-push)
* [bintray/bintray-examples](https://github.com/bintray/bintray-examples)

# 番外

> 有问题？加 qq 群：453503476，希望能帮到你。

# License

    Copyright 2016 kvh

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.