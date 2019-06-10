TACT - Resources
=============

What is this?
-------------

Definition files for libraries validated in new projects.

To define :
- Component versions
- Plugins gradle
- Dependency libraries


Type of Project
-------------

- Spring-Boot (Java)
- Android (Java & kotlin)

How To Use
-------------

Apply version file on your project.
You can use URL from repository or local copy (for Network issues).

#### from master (rolling release):

```Groovy
apply from: "https://github.com/TACTfactory/tact-resources/raw/master/springb_version.gradle"
```

#### for specific version / commit / release:

```Groovy
apply from: "https://github.com/TACTfactory/tact-resources/raw/865893072b783680bf46bdf28bb1a21c736d2bf9/version.gradle"
```

After you use your gradle files.

eg. Android

```Groovy
android {
    compileSdkVersion config.version.android.compileSdk
    buildToolsVersion config.version.android.buildTool

    defaultConfig {

        minSdkVersion config.version.android.minSdk
        targetSdkVersion config.version.android.targetSdk
    }
    
    dependencies {
        implementation lib.android.x.appcompat
        implementation lib.android.x.cardview
        implementation lib.android.x.constraintlayout
        implementation lib.android.material
        
        implementation lib.android.supportDeprecated.palette
        
        compileOnly lib.lombok
        annotationProcessor lib.lombok
    }
}
```

#### Extra

> Tips: Apply entry in "buildscript" for global access.
> ```groovy
> buildscript {
>     apply from: "https://github.com/TACTfactory/tact-resources/raw/master/springb_version.gradle"
>
>     // NOTE: Can be used has this level.
>     dependencies {
>         classpath gradlePlugin.android.build
>         classpath gradlePlugin.netflix.gradleLint
>     }
> }
> ```

## Contributing

If you want to contribute code to this project, first you need to fork the project. The next step is to send a pull request (PR) for review. The PR will be reviewed by the project team members. Once you have gained "Look Good To Me (LGTM)", the project maintainers will merge the PR.

## License

This project abides by Apache License 2.0.
