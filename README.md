# How to publish a module to maven

1.In project `build.gradle` .Add

```
buildscript {
...
    dependencies {
        classpath 'com.novoda:bintray-release:0.8.0'
    }
}
```
2. In module `build.gradle` .Add on top of file

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

userOrg: organization name //must same at on bintray
repoName: repository name // must same at on bintray
groupId: directory contain artifactId package
artifactId: package name

3. Run on terminal
`./gradlew clean build bintrayUpload -PbintrayUser=YOUR_USER_NAME -PbintrayKey=YOUR_KEY -PdryRun=false --stacktrace`



