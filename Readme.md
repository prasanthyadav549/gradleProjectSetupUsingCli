# Setup of basic using cli:
```agsl
gradle init --use-defaults --type java-application
```
The above command will setup a basic gradle project.

```agsl
./gradlew build
```
To prepare a jar which is executable, you need to setup manifest property in `build.gradle` to identify which is the main class to execute.

```groovy
manifest {   // manifest defines where the execution of the whole program starts from.
        attributes(
                'Class-Path': configurations.runtimeClasspath.files.collect { it.getName() }.join(' '),
                'Main-Class': 'org. example.Main'
        )
    }
```
the above command can build your project.


```agsl
./gradlew jar
```

The above command creates a new jar file in `builds/libs` folder.


```agsl
java -jar build/libs/{jar-file-name}
```

The above command will execute your code.
