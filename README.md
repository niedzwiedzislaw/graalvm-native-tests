# Simple java native application
Official docs: https://www.graalvm.org/22.1/reference-manual/native-image/

In the end, the executable does not start significantly faster than jar run by java. 

## Setup
1. A C compiler has to be installed
    1. For windows that can be either
       1. Visual Studio Community/Pro/Enteprise
       2. Visual Studio Build Tools (cmd line utilities only, no IDE)
2. 'Native' has to be installed in GraalVM
   
    ```gu install native-image```

## Creating an executable
### Windows
When creating an executable file the compiler has to be in the PATH. On Windows, Visual Studio cmd line environment has to be initialized for specific architecture with command 

```c:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Auxiliary\Build\vcvarsamd64_x86.bat```. 

Also, Manifest has to be present in jar file.

1. javac App.java
2. jar cfv App.jar App.class META-INF
3. native-image -jar App.jar