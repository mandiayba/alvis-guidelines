
# Alvis module: elements and convention {#alvis-module-elements-and-conventions}

The minimal  components required to create a module are a **module class** \(a Java Class\) and a **module description** \(a XML file\). The module class contains the implementation of the module and the module description contains the documentation about the module and its parameters. The class file must be present into source forder \(`src/main/java/*`\) and the description file must be present into resource folder \(`src/main/resources/*`\), as shown in the exemple bellow.
![](/assets/module_folder.png)

### Implement the Module Java Class
As shown in the following Skeleton, the module class extends the [`CorpusModule`](### Corpus Class) defined into AlvisNLP. Its main method is `process` whose arguments are the [`ProcessingContext<Corpus>`](processingcontext) and [`Corpus`](#corpus) objects. The `ProcessingContext<Corpus>` object allows to access the context of the execution, for examples the log and system settings. `Corpus` corresponds to the [internal data structure](/alvis_internal_data_model.md) of Alvis, it contains the main input and output data to be processed by the module. You must implement the task of the module into the `process` method, by accessing the input data from the  `Corpus` object and writing the outputs into the same `Corpus` object. 

> Note that, implementing a module requires you to know the [Alvis Internal Data Model](/alvis_internal_data_model.md) accessible through the `Corpus` class. If your module uses a special data structure, you have to implement the adapters methods between the module's `specific data structure` and `Corpus.`


For the module to an valid module, you must use conventional Java annotations, the two principal are `@AlvisNLPModule` and `@Param.` `@AlvisNLPModule` is required for the class to be recognized by Alvis as a valid module. `@Param` is for Alvis to recognize the specific parameters of the module. It must annotate each getter method \(and also the setter method\) that get the parameter value \(and also to set the parameter value\) of the module. A detailled presentation of the Java annotation used into AlvisNLP are here.
```
@AlvisNLPModule
public class MyModule extends CorpusModule<ResolvedObjects> {

    @Override
    public void process(ProcessingContext<Corpus> ctx, Corpus corpus) throws ModuleException {
        ...
    }

    @Param
    AParamType getNameOfAParam(){
    ...
    return ...
    }

    @Param
    void setNameOfAParam(AParamType aParamTypeObject){
    ...
    }

    ...
}
```

> Although, most of the time the module class requires just to extend the [`CorpusModule`](#corpusmodule), it can extends or implements other interfaces and classes for specific needs \(see here for the details\).
 
### Declare the Module XML Description
The module description is partially generated from the module Class. By convention, its name correponds to the name of the module class with the `Doc` string appended \(e.g., for `MyModule.java),`the name of the module description is `MyModuleDoc.xml`\). You must complete the description taking care of providing information needed to understand the module. An example of module description is presented [here](/alvis_module_description.md).
