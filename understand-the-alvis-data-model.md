# Internal Data Model
The data structure is responsible for holding the corpus contents to consume, process and produce by the modules into Alvis. The data structure is seen as a global shared variable from which each primitive module, during its execution, read its inputs and write its outputs. The content of the variable evolves during execution of the modules. The modules are executed only in a sequential mode, they can add new contents but don't modify the existing ones.


The structure provides basic elements that are features, Annotations, Tuples that hold the basic information. It also provides container that are Layers and Relations that organize the contents and provides the typical elements Section, Document and Corpus that hold information about textual articles.

![](/assets/alvisdatamodel.png)

* **Corpus, Documents and Sections** serve respectivelly to contain corpus, documents and sections. A corpus is composed of a set of documents and a document is composed of a list of sections. A section contains a set of layers and a set of relations.
* **Layers and Relations** organize the respectivelly the annotations and the tuples. A layer contains a set of annotations and a Relation contains a set of tuples.
* **Annotations and Tuples** contain respectivelly information on text span and links between several spans. An annotation delimits a span in a text in a stand off manner. A tuple group all the elements (e.g., annotation, relation) that have dependence each other. The following figure examples of information annotation and Tuple allow to capture.
* **Features** contain information about tags, labels, categories, etc. A feature is a ```(key, value)``` pair, where a ```key``` content is associated to a ```value```. Each element corpus, Document, Section, Annotation or Tuple contains features, the features are used to set information to these elements. The following example illustrate the usage of the features.

 ** This feature  ```(set, Test)```, where ```key=set``` and ```value=test``` can be used to tell that a corpus is test set corpus.
  
 ** This  feature  ```(pos, NN)```, where ```key=pos``` and ```value=NN``` can be used to set the part-of-speech of an annotation.
 
 ** This  feature  ```(type, Protein)```, where ```key=type``` and ```value=Protein``` can be used to set a named-entity.



