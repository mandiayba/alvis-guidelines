```
<?xml version="1.0" encoding="UTF-8"?>
<alvisnlp-doc author="" beta="false" date="" resource-list="modules" resource-type="module" short-target="HelloWorld">
  <synopsis>
    <p> hello world says <p> hello </p> to the world </p>
  </synopsis>
  
  <module-doc>
    <description>
      <p>
       HelloWorld says hello World in differents languages. It uses the parameters <param name="the_sentence"/> and <param name="the_language"/>.
      <p>
    </description>
  
    <param-doc default-value="Hello World" mandatory="true" name="the_sentence" short-type="String[]" type="java.lang.String[]">
      <p> the sentence hello world /p>
    </param-doc>
        
    <param-doc 
        default-value="EN" mandatory="false" name="the_language" short-type="the_short_type_of_the_parameter" type="the_type_of_the_parameter">
      <p> a descripion of my special parameter/p>
    </param-doc>
</module-doc>
</alvisnlp-doc>
```