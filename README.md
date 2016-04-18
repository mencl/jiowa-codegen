# [jiowa-codegen](http://www.jiowa.de/download.html)

#[JIOWA Code Generation &amp; Template Engine](http://www.jiowa.de/download.html)

## Features
* compile-time safety for your templates,
* full control of code generation & template engine via Java,
* very effective and comprehensible template notation,
* template notation symbols can be changed dynamically according to your target platform,
* strict separation of code (generator) and design (template), 
* templates do not carry any model-specific information ==> completely re-usable across different projects,
* supports any type of model for which an API exists,
* supports each IDE (no plug-ins necessary),
* easily extensible via Java,
* no polyglot programming.

##**Quick Introduction:** Letter Example

Below we see a simple example template for a letter or email.

![](http://www.jiowa.de/_Media/folie-04_med.png)


Templates are simple text files which can be enriched with template notation elements in order to work with parameters.

![](http://www.jiowa.de/_Media/folie-05_med.png)


There are only two basic structures for parameters: variables and subtemplates. In the example letter, inline subtemplates are used, a special case of subtemplates. The red template notation elements are symbols only. There are no special keywords. The green identifiers can be chosen arbitrarily by the user.

![](http://www.jiowa.de/_Media/folie-06_med.png)


The template is compiled during the automatic build process into a so-called template bean. The green text elements of the template become nested structures (classes, constants, ...) within the template bean class.

![](http://www.jiowa.de/_Media/folie-07_med.png)


Parameters can be simply filled into the template bean as shown in the lower left part of the next picture. The text representation of the template bean Letter_jgt delivers the template text with inserted parameter values ("Smith", "Jenny Jones") and sub template instances (Mr, Ms).  The text representation of sub template Mr via the toString()-method is "Mr.". 

![](http://www.jiowa.de/_Media/folie-08_med.png)


The output of the toString()-method of template bean Letter_jgt is shown in the lower right of the picture below.

![](http://www.jiowa.de/_Media/folie-09_med.png)


##**Quick Introduction:** Java Class Template

The next example shows a Java class template which uses two additional sub templates: Attribute.jgt & GetterSetter.jgt. 

![](http://www.jiowa.de/_Media/folie-11_med.png)

The sub template structure identifiers like "foreachAttribute" can be chosen by the template designer totally arbitrarily. It does not matter if we write "pourChaqueElement" (french) or "fuerJedesAttribut" (german), or separate the single words with spaces as in "for each attribute".  This identifier is always compiled into the corresponding structure within the template bean with the same name and can be used for the (multiple) insertion of subtemplate instances.

![](http://www.jiowa.de/_Media/folie-12_med.png)


The picture below depicts the translation of the Java class template into the template bean class via automatic build of your IDE.

![](http://www.jiowa.de/_Media/folie-13_med.png)

The attribute template Attribute.jgt is rather short and consists of only two variable values: DataType,  AttributeName.

![](http://www.jiowa.de/_Media/folie-14_med.png)

Getters and Setters are defined in the GetterSetter.jgt template which is compiled into the template bean class GetterSetter_jgt.

![](http://www.jiowa.de/_Media/folie-15_med.png)

Insertion of values into the Java class template is performed in the same way as in the letter template example. The type of model from which the data is obtained to be inserted into the template beans is totally arbitrary as the templates are obviously completely independent from any kind of model.

[Download the code generation framework here ...](http://www.jiowa.de/download.html)

##License
JIOWA Code Generation Framework & Template Engine is licensed under the 
[JIOWA Backlinking License 1.0](http://www.jiowa.de/jiowa-codegen-license.html)


