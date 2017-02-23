# 

# Deploying a module into AlvisNLP

AlvisNLP is a processing...

In the following, we present in the following

1. the elements and convention to create a module : this part presents meterials needed to implement a module into Alvis. The tasks implied here are done by Java developers.
2. how the module is recognise and added to the AlvisNLP system : this part, shows how a implemented module is recognized, compiled and integrated into the Alvis System. All required is by default present into the Alvis system for this step to be done automatically.
3. how the module into the system is loaded and executed : this part presents the module execution. It also concerns the interface acces for the module. 

Note that, in a

## Alvis module: elements and convention

The minimal  element required to create a module are the **module Class** \(a Java Class \) and the **module Description** \(a XML file\). The module Class contains the implementation of the module and the module description contains the documentation about the module and its parameters. The module Class file must be present into source forder \(`src/main/java/*`\) and the module description file must be present into resource folder \(`src/main/resources/*`\). See bellow for an example.

![](/assets/Capture du 2017-02-23 15:01:41.png)



As shown in the following Skeleton, the module class extends the [`CorpusModule<ResolvedObjects>`][corpusmodule] defined into AlvisNLP. Its main method is`process` whose arguments are [`ProcessingContext<Corpus>`][processingcontext] and [`Corpus`][#corpus] objects. The `ProcessingContext<Corpus>`allows to access the context information related to the execution of the module. `Corpus` is the internal data model of AlvisNLP, it contains the main input and output data processed by the module. Note that, depending to the needs, the module class can extends or implements other interfaces and classes \(see here for the details\).

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

The module description is partially generated from the module Class. By convention, its name correponds to the name of the module class with the append "Doc" at the end \(e.g., for `MyModule.java),`the name of the module description is   `MyModuleDoc.xml`\). The

## Alvis module: recognition and integration

## Alvis module: loading and execution

## **Alvis main classes and Interfaces**

### Corpus Class {#corpus}

### Corpus Module Class {#corpusmodule}

### Proccessing Context Class {#corpuscontext}



