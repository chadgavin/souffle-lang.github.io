---
title: Swig
permalink: /Swig
sidebar: docs_sidebar
folder: docs
---
 
SWIG is software development tool that connects programs written in C and C++ with a variety of high-level programming languages. Soufflé uses SWIG as a programming interface such that other languages can interface it. Swig Interface currently supports **Java**  and **Python**.

## Usage 

To run the SWIG command line option in Souffle, run :

```./souffle -s<language> <.dl file> ```

The languages given must be all lowercase.

### Running it in Java
To use the interface in your Java program, add 

```System.loadLibrary("SwigInterface")```

MAC users may need to add this instead

`System.load(System.getProperty("java.library.path")+ "/" + "libSwigInterface.so")`

You are now able to use the SwigInterface to create an instance of the input file to be loaded and run.

`SWIGSouffleProgram p = SwigInterface.newInstance("<name of .dl file without extension>")`

`p.loadAll(".");`

`p.run(); `

`p.printAll(".");`

`p.finalize();   ` 

Compile your program and run it with the -D option to specify the directory of your SwigInterface

`java -Djava.library.path=<path of SwigInterface> <.java>`

### Running it in Python
To use the interface in your Python program, add at the top of the file
`import SwigInterface`

You are now able to use the SwigInterface to create an instance of the input file to be loaded and run.

`p = SwigInterface.newInstance("<name of .dl file without extension>")`

`p.loadAll('.')`

`p.run()`

`p.printAll('.')`

Run your program to see the outputted CSV files.
 
