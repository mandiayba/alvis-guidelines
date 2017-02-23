

## Alvis module: elements and convention {#alvis-module-elements-and-conventions}

The minimal  element required to create a module are a **module class** \(a Java Class\) and a **module description** \(a XML file\). The module class contains the implementation of the module and the module description contains the documentation about the module and its parameters. The class file must be present into source forder \(`src/main/java/*`\) and the description file must be present into resource folder \(`src/main/resources/*`\). See bellow for an example.

![](/assets/Capture du 2017-02-23 15:01:41.png)



As shown in the following Skeleton, the module class extends the [`CorpusModule`](### Corpus Class) defined into AlvisNLP. Its main method is `process` whose arguments are [`ProcessingContext<Corpus>`](processingcontext) and [`Corpus`](#corpus) objects. The `ProcessingContext<Corpus>` object allows to access the context of the execution, for examples the log and system settings. `Corpus` corresponds to the data model of AlvisNLP, it contains the main input and output data to be processed by the module. Although by default the module class extends the [`CorpusModule`](### Corpus Class), depending to the needs it can extends or implements other interfaces and classes \(see here for the details\).

The module class accepts some conventional Java annotations, the two principal are `@AlvisNLPModule` and `@Param`. `@AlvisNLPModule` is required for the class to be considered as a valid Alvis module. `@Param`is used on each getter method \(and also the setter method\)  to get a specific parameter value \(and also to set a specific parameter value\) of the module. The parameters of the module are identified by the `@Param` annotation. An individual parameter is identified by the name of the getter \(and setter\) method, its value is determined by the type the getter method returns \(which corresponds to the value the setter method accepts\). A detailled presentation of the Java anonotation used into AlvisNLP are here.

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

The module description is partially generated from the module Class. By convention, its name correponds to the name of the module class with the `Doc` string appended \(e.g., for `MyModule.java),`the name of the module description is   `MyModuleDoc.xml`\). The
