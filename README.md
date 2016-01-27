[中文文档](README_CN.md)

# Introduction
This is a gradle plugin collection for `publish maven package`, which includes the following sollution:

* localrepo：publish package to local maven repo
* bintrayaar：publish `aar` package to bintray repo
* bintrayjar：publish `jar` package to bintray repo
* sonatypearr：publish aar package to sonatye maven central repo

The coresponding android studio modules explains how they work.

This is a `side project` of my tutorial serial: embrace-android-studio, and there is only Chinese version, and I have plan to translate it into English, so stay tuned!

[embrace-android-studio: maven-deploy](http://kvh.io/2016/01/20/embrace-android-studio-maven-deploy/)

# localrepo

remember to change the content of `localrepo/gradle.properties` to your setting, especially:

```
LOCAL_REPO_URL=file:///Users/your-user-name/Documents/Android/repo/
```

call following code to build and upload:

```
$ ./gradlew -p localrepo clean build uploadArchives --info
```

# bintrayaar | bintrayjar
change `bintrayaar/local.properties` or `bintrayjar/local.properties`:

```
bintray.apikey=your-api-bintray-key
bintray.user=your-bintray-user
bintray.gpg.password=your-gpg-password
```

# sonatypeaar

change `sonatypeaar/local.properties`

```
NEXUS_USERNAME=admin
NEXUS_PASSWORD=admin123
RELEASE_REPOSITORY_URL=http://192.168.99.100:8081/content/repositories/releases
SNAPSHOT_REPOSITORY_URL=http://192.168.99.100:8081/content/repositories/snapshots
```

# Acknowledgements

Thanks to the following people(organization), i just get the plugins from them:

* [chrisbanes/gradle-mvn-push](https://github.com/chrisbanes/gradle-mvn-push)
* [bintray/bintray-examples](https://github.com/bintray/bintray-examples)

# help
just report a issue and i will response to it.


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