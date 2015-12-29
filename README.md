# autocomplete-java

Autocomplete-plus provider for Java. Features:

* Complete package and class names
* Import classes
* Organize imports
* Examine public methods and properties of a class or instance and use them as snippets
* Crude determination of type
* Intelligent suggestions (remembers previous selections)
* Refresh class description automatically on save (after compile)
* Refresh all class descriptions manually with the refresh command

Official page for package at atom.io: [autocomplete-java](https://atom.io/packages/autocomplete-java)

## Preview

![Screenshot](https://raw.github.com/keskiju/autocomplete-java/master/screenshot.gif)

## Usage

Configure classpath via a .classpath file that is placed at the root directory of your project. For example:

    ./src:./classes:./lib/*

You can also alter autocomplete behavior with package settings.  

NOTE:
* Autocomplete starts to work for method calls of a class once it has been analyzed. Current implementation is still unoptimized, however, so please be patient. Analyzing all classes will take a while, especially for JDK libraries which are loaded last. Class loading will be optimized later.
* If package fails to determine type of variable or method return value automatically, you can still examine members of a class using class name e.g. 'ArrayList.con...'. Type determination will be improved in the future.
* Package requires that either JAVA_HOME environment variable is set or java commands are found on path.
* This package requires compiled classes to function, but it does not compile classes from source. Use other tools for compiling.

Tips:
* At first, compile all your classes using your favorite build tool, and start your app.
* Lint and compile changed classes automatically on save with [linter-javac](https://atom.io/packages/linter-javac). Autocomplete-java refreshes class description automatically on save. NOTE: linter-javac compiles classes only if none of them contain any errors. Therefore you have to run 'project refresh' (shift-ctrl-alt+R) manually after you fix an error, if it causes compilation of multiple changed classes at once.
* Reload changed classes automatically in JVM with [spring-loaded](https://github.com/spring-projects/spring-loaded) or some other JVM agent.

## TODO

For v1.0.0:
* Unit tests
* Optimize 'load class members'
* Fine tuning and small fixes

Later:
* Autocomplete constructors
* Autocomplete boilerplate implementations of getter and setter methods
* Autocomplete boilerplate implementations of inherited methods
* Show parameter names in method suggestions
* Show inherited methods in method suggestions
* Go to method declaration
* Intelligent determination of type (current implementation is just a quick hack)
* Support for multiple root folders
* Support for symlinks
* Fuzzy search

Check all open issues at [GitHub issues](https://github.com/keskiju/autocomplete-java/issues)

## Contribute

Contributions are welcome. Please comment on [issues](https://github.com/keskiju/autocomplete-java/issues) you would like to contribute to, or add feature requests of your own.
