[![Build Status](https://travis-ci.com/tiohlognm/java-sdk.svg?branch=master)](https://travis-ci.com/joaomlneto/travis-ci-tutorial-java)
[![Code Coverage](https://codecov.io/github/tiohlognm/java-sdk/coverage.svg)](https://codecov.io/gh/joaomlneto/travis-ci-tutorial-java)

# Java Project Template

Template with CI/CD and README.

## Dependencies

#### JVM, SDK etc

Install jvm dll https://www.java.com/de/download/windows_offline.jsp 

#### Settings 

Add External/settings.xml to your home directory, folder .m2: 
C:\Users\<User ID>\.m2

## Using Maven
Before you start using Maven, be sure to have the environment variable `JAVA_HOME` set.
It should have a value of something like this:

`C:\Program Files\Java\jdk1.8.0_241` be sure to point to `JDK`, not `JRE`!

Now you should be able to run the `mvn install` command in the project root directory. This will create 
a `target/` directory in the project root directory.

Same could be achieved with IntelliJ Maven Plugin:

To add a project as a Maven project - RMB on `pom.xml` and choose `Add as Maven Project`.

After that a Maven Plugin tab should appear on the upper right corner. There you should see an `m` button - click on
 it and type `mvn install`. The project jar will be compiled into the `target/` directory. Use the jar `java-jdk-VERSION-jar-with-dependencies.jar` as you would use any other jar.
 
 If you are using IntelliJ IDEA IDE and after installing Maven dependencies you have some classes not imported
 or other errors, reload IDEA.   

## Preparing jar file

To successfully use this module, creation of a jar file from a module is required:

#### If you are using IntelliJ IDEA IDE:

In IDEA, go to `File` > `Project Structure...` > `Artifacts` > `+` > `JAR` > `From module with dependencies`

Fill the field Main class with `example.launcher.Main`.

Check, in `File` > `Project Structure...` > `Modules` > `java-sdk` > `Dependencies`
- Module SDK: Project SDK 1.8
- java version 1.8 
- `+` `->` `JAR or directories`, add folder `External` of this repository. Enable the checkbox.

After, go to `Build` > `Build Artifacts...` > `your_artifact` > `Build`

The new directory "out" will appear with jar file within: 

    out/artifacts/java-sdk/java-sdk.jar

Name of a jar file can vary depending on your choices.

### Build automation 

#### Travis 
https://docs.travis-ci.com/user/languages/java/


## Code Coverage with CodeCov

This repository also integrates with Codecov to generate reports.

- The [JaCoCo](https://www.jacoco.org) plugin is included in `pom.xml`
- On `.travis.yml`, `after_success` target executes the Codecov script.

If you want to use it:
- Go to the Codecov website and create an account and setup permissions.
- Add your repository (you can go there directly by going to https://codecov.io/gh/your-github-username/travis-ci-tutorial-java)
- Fix the `README.md` badge.