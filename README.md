# gradle-bintray-plugin

> Publish your android/java libraries to bintray.

1. Add official bintray plugin.

```gradle
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.8.4'
    }
}
```

2. Config secret info in `local.properties`.

Note: this file shouldn't be included in vcs.
```
BINTRAY_USER=your bintray account
BINTRAY_API_KEY=your bintray api key
```

3. Config library info in `build.gradle` of the library.
 - Example ext for Ophelia library.

```gradle
ext{
    bintrayRepo = "Ophelia"
    bintrayName = "com.ahmetkilic.ophelia"

    libraryName = "ophelia"

    publishedGroupId = "com.ahmetkilic.ophelia"
    artifact = "ophelia"
    libraryVersion = "1.0.2"

    libraryDescription = "Ophelia framework for android."
    siteUrl = "https://github.com/ahmet12/ophelia"
    gitUrl = "https://github.com/ahmet12/ophelia.git"

    developerId = "ahmetkilic"
    developerName = "Ahmet Kılıç"
    developerEmail = "41ahmetkilic@gmail.com"

    licenseName = "The Apache Software License, Version 2.0"
    licenseUrl = "https://www.apache.org/licenses/LICENSE-2.0"
    allLicenses = ["Apache-2.0"]
}
```

4. apply script from remote.
`apply from: 'https://raw.githubusercontent.com/ahmet12/gradle-bintray-plugin/master/publishing.gradle'`

## Install and Upload to Bintray
```
gradlew clean build
gradlew install
gradlew bintrayUpload
```


