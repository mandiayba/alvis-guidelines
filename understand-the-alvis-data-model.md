# Internal Data Model
The data structure is responsible of holding  corpus contents that are consumed, processed and produced by a sequence of Alvis modules. It is seen as a global shared variable from which each primitive module  read its inputs and write its outputs.


The data structure provides   elements (_Corpus_, _Document_ and _Section_) that hold the typical information about textual articles. It also provides elements (_Annotations_, _Tuples_ and _Features_) to capture  annotations, events and features of a corpus. Containers consisting of _Layers_ and _Relation_ allow to group the information about the elements. The following figure presents an abstraction of the elements and their composition.

![](/assets/alvis_data_model.png)

* **Corpus, Documents and Sections** respectively serve to contain corpus, documents and sections. A corpus is composed of a set of documents and a document is composed of a list of sections. A section is composed of a text content, a set of layers and a set of relations.
* **Layers and Relations** respectively organize  annotations and  tuples. A layer contains a set of annotations and a Relation contains a set of tuples.
* **Annotations and Tuples** contain respectivelly information on text tokens and links between several tokens or between elements. An annotation delimits a token in a text with start and end coordonates. A tuples groups all elements (e.g., annotations, relations) that have link each other. Each tuple express a link that is composed of the role of the link and the element concerned by the link.
* **Features** contain information about tags, labels, categories, etc. of an element. Features are ```(key, value)``` variable pairs, where the content of variable ```key```  is associated to the content of variable ```value```. Each element _Corpus_, _Document_, _Section_, _Annotation_ or _Tuples_ has _Features_. The following example illustrate the usage of the features.

 **    This feature  ```("set", "Test")```, where ```key="set"``` and ```value="Test"``` can be used to tell that a corpus is test set corpus.
 
 **    This  feature  ```("pos", "NN")```, where ```key="pos"``` and ```value="NN"``` can be used to set the part-of-speech of an annotation.
 
 **    This  feature  ```("type", "Protein")```, where ```key="type"``` and ```value="Protein"``` can be used to set a named-entity.



