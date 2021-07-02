# Processing Mode Template
This is an example setup to create a new mode in [Processing](https://processing.org/). It extends Processing's default Java mode, though you can easily remove the Java mode dependencies to create a mode for a different language.

## Credits
The mode templates for previous versions created by [Martin Leopold](https://github.com/martinleopold/TemplateMode) and [Joel Moniz](https://github.com/joelmoniz/TemplateMode/tree/3.0-compatibility) provided a guide for this template.

This repository is a GitHub template and has some unnecessary files removed. It also works on newer Processing versions (tested on 3.5.4).

## Setup Instructions
TODO

## Converting This Mode to a Non-Java Mode
The template mode in this repository extends Java mode. In other words, it functions identically to Java mode, but you could add more features to Java mode if you wanted.

If you don't want to extend Java mode, there are only a few changes that you need to make. Java mode-specific snippets have a comment above them starting with `JAVA MODE:`.

### Your Mode Class ([ProcessingMode.java](src/io/github/soir20/processingmode/ProcessingMode.java))
To make a general mode, this class should extend `processing.app.Mode` and implement its methods instead of extending `processing.mode.java.JavaMode`. You also don't need to use Java's class loader. Unless you need it, you can remove the `getClassLoader()` method entirely.

### [build.xml](build.xml)
There are two snippets marked with `JAVA MODE:` in this file.

The first includes Java mode's dependencies in the classpath.

The second includes copies resource files (such as icons and keywords) into your build. Processing won't fall back to Java mode's theme, so it won't be able to find those files if you don't copy them.

Remove both of these snippets if you don't want to extend Java mode.

### [build.properties](build.properties)
You can define build properties directly in build.xml if you wish, but this file separates them to make them clearer and easier to find.

There are several properties in this file that you can remove if you are not using Java mode:
* `processing.java` - the location of Java mode in the Processing source code
* `processing.java.mode` - the location of the Java mode .jar files in the Processing source code
* `processing.java.theme` - the location of the theme icons for Java mode. Ant copies this directory into your mode when it is built.
* `processing.java.keywords` - the location of the keywords.txt file for Java mode. Ant copies this file into your mode when it is built.
* `processing.java.suggestions` - the location of the suggestions.txt file for Java mode. Ant copies this file into your mode when it is built.

### [mode.properties](resources/mode.properties)
The `imports=` line is necessary to make this mode depend on Java mode. Remove this if you don't want to extend Java mode.