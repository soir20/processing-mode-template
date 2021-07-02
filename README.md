# Processing Mode Template
This is an example setup to create a new mode in [Processing](https://processing.org/). It extends Processing's default Java mode, though you can easily remove the Java mode dependencies to create a mode for a different language.

## Credits
The mode templates for previous versions created by [Martin Leopold](https://github.com/martinleopold/TemplateMode) and [Joel Moniz](https://github.com/joelmoniz/TemplateMode/tree/3.0-compatibility) provided a guide for this template.

This repository is a GitHub template and has some unnecessary files removed. It also works on newer Processing versions.

## Setup Instructions
TODO

## Converting This Mode to a General Mode
There are a few snippets in the build setup that are specific to creating a mode that extends Java mode. These snippets have a comment above them starting with `JAVA MODE:`. In particular, there are two inclusions of Java mode files in build.xml, source locations in build.properties, and an imports line for Java mode in mode.properties.