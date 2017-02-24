# Integrate the module source to AlvisNLP {#alvis-module-loading-and-execution}

The previous [chapter](alvis_module_elements_and_conventions) presents how to create a valid alvis module. Now we will present how the module is integrated and how Alvis recognizes it.

First, the source of the module must be added to the [Alvis source here](https://github.com/Bibliome/alvisnlp/tree/master/bibliome/src/main). That alvis source folder is localized in maven project that only contains libraries of alvis modules. One way to add module source is to checkout the Alvis source and copy the module source as follow.
```
$git clone https://github.com/Bibliome/alvisnlp.git
$cp -r path_to_the_module_src/ alvisnlp/bibliome/src
```

After the previous step, the module is ready to be packaged with Alvis. For that you have just to compile the alvisnlp project with maven.
```
$mvn compile
```

If the compilation pass, the module is recognized and packaged into Alvis. Now what happened during compilation? The first thing is that an Alvis annotation processor has recognized the module and its parameters from the Java annotations. The compiler also verifies the coherence of the module. This is followed by the generation of resources of the module.

  
