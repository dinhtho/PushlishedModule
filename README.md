# How to publish a module to maven

1 .In project `build.gradle` .Add

```
buildscript {
...
    dependencies {
        classpath 'com.novoda:bintray-release:0.8.0'
    }
}
```
2 . In module `build.gradle` .Add on top of file

` apply plugin: 'bintray-release'`

and at bottom

```
publish {
    userOrg = 'tho'
    repoName = 'tho'
    groupId = 'com.dinhtho'
    artifactId = 'SectionDecoration'
    publishVersion = '1.0'
    desc = 'Support header for recyclerview'
    licences = ['Apache-2.0']
    website = 'https://github.com/dinhtho/StickyHeaderSection'
}
```

userOrg: organization name //must same at on bintray <br />
repoName: repository name // must same at on bintray <br />
groupId: directory contain artifactId package  <br />
artifactId: package name


More information about configurations reference at https://github.com/novoda/bintray-release/wiki/Configuration-of-the-publish-closure

3 . Run on terminal
`./gradlew clean build bintrayUpload -PbintrayUser=YOUR_USER_NAME -PbintrayKey=YOUR_KEY -PdryRun=false --stacktrace`



