# gradle-code-quality-tools-plugin

[![Build Status](https://travis-ci.org/vanniktech/gradle-code-quality-tools-plugin.svg)](https://travis-ci.org/vanniktech/gradle-code-quality-tools-plugin)
[![License](http://img.shields.io/:license-apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)
![Java 7 required](https://img.shields.io/badge/java-7-brightgreen.svg)

Gradle plugin that generates Findbugs-, Checkstyle- and PMD Tasks for every subproject. All of the taks will also automatically hook into the build lifecycle.

Works with the latest Gradle Android Tools version 1.5.0. This plugin is compiled using Java 7 hence you also need Java 7 in order to use it.

# Set up

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath 'com.vanniktech:gradle-code-quality-tools-plugin:0.1.0'
    }
}

apply plugin: 'com.vanniktech.code.quality.tools'
```

## Configuration (since 0.2.0)

This configuration is shown with default values.

```groovy
codeQualityTools {
    failEarly = true
    xmlReports = true
    htmlReports = false
    ignoreProjects = []

    findbugs {
        toolVersion = '3.0.1'
        excludeFilter = 'code_quality_tools/findbugs-filter.xml'
    }

    checkstyle {
        toolVersion = '6.14.1'
        configFile = 'code_quality_tools/checkstyle.xml'
    }

    pmd {
        toolVersion = '5.4.1'
        ruleSetFile = 'code_quality_tools/pmd.xml'
    }
}

```

Information: [This plugin is also available on Gradle plugins](https://plugins.gradle.org/plugin/com.vanniktech.code.quality.tools)

### Snapshots

Can be found [here](https://oss.sonatype.org/#nexus-search;quick~gradle-code-quality-tools-plugin). Current one is:

```groovy
classpath 'com.vanniktech:gradle-code-quality-tools-plugin:0.2.0-SNAPSHOT'
```

# License

Copyright (C) 2016 Vanniktech - Niklas Baudy

Licensed under the Apache License, Version 2.0