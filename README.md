[**Download** jiowa-codegen](http://www.jiowa.de/download.html)


#[JIOWA Code Generation &amp; Template Engine](http://www.jiowa.de/download.html)

A new approach for code generation is presented. It consists of a powerful template engine which works quite differently from other approaches.

Templates are pre-compiled during automatic build of the IDE into so-called _template beans_ (POJOs). By design, application logic is written in user-defined Java code which uses template beans for the data insertion process. Each template bean can render its contents to a text string by simply calling the `toString()`-method. If previously generated source files have to be updated, the code generation framework also offers support for protected regions which leave manually written text regions unchanged. 


## Features
* [**_compile-time safety_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/13) for your templates,
* [**_full control of code generation & template engine via Java_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/8),
* very [**_effective and comprehensible template notation_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/24),
* [**_template notation symbols can be changed dynamically_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/40) according to your target platform if needed,
* strict [**_separation of code_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/9) (generator) [**_& design_**](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/9) (template), 
* **_templates_** do not carry any model-specific information ==> **_completely re-usable across different projects_**,
* **_supports any type of model_** for which an API exists,
* **_supports each IDE_** (no plug-ins necessary),
* easily **_extensible via Java_**,
* **_no polyglot programming_**.

##**Quick Introduction:** Letter Example

Below we see a simple example template for a letter or email.

![](http://www.jiowa.de/_Media/folie-04_med.png)


Templates are simple text files which can be enriched with [template notation elements](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework/25) in order to work with placeholders.

![](http://www.jiowa.de/_Media/folie-05_med.png)


There are only two basic structures for placeholders: variables and subtemplates. In the example letter, inline subtemplates are used, a special case of subtemplates. The red template notation elements are symbols only. There are no special keywords. The green identifiers can be chosen arbitrarily by the user.

![](http://www.jiowa.de/_Media/folie-06_med.png)


The template is compiled during the automatic build process into a so-called template bean. The green text elements of the template become nested structures (classes, constants, ...) within the template bean class.

![](http://www.jiowa.de/_Media/folie-07_med.png)


Parameters can be simply filled into the template bean as shown in the lower left part of the next picture. The text representation of the template bean `Letter_jgt` delivers the template text with inserted parameter values ("Smith", "Jenny Jones") and sub template instances (`Mr`, `Ms`).  The text representation of sub template Mr via the `toString()`-method is "Mr.". 

![](http://www.jiowa.de/_Media/folie-08_med.png)


The output of the `toString()`-method of template bean `Letter_jgt` is shown in the lower right of the picture below.

![](http://www.jiowa.de/_Media/folie-09_med.png)


##**Quick Introduction:** Java Class Template

The next example shows a Java class template which uses two additional sub templates: `Attribute.jgt` & `GetterSetter.jgt`. 

![](http://www.jiowa.de/_Media/folie-11_med.png)

The sub template structure identifiers like "`foreachAttribute`" can be chosen by the template designer totally arbitrarily. It does not matter if we write "`pourChaqueElement`" (french) or "`fuerJedesAttribut`" (german), or separate the single words with spaces as in "`for each attribute`".  This identifier is always compiled into the corresponding structure within the template bean with the same name and can be used for the (multiple) insertion of subtemplate instances.

![](http://www.jiowa.de/_Media/folie-12_med.png)


The picture below depicts the translation of the Java class template into the template bean class via automatic build of your IDE.

![](http://www.jiowa.de/_Media/folie-13_med.png)

The attribute template `Attribute.jgt` is rather short and consists of only two variable values: `DataType`,  `AttributeName`.

![](http://www.jiowa.de/_Media/folie-14_med.png)

Getters and Setters are defined in the `GetterSetter.jgt` template which is compiled into the template bean class `GetterSetter_jgt`.

![](http://www.jiowa.de/_Media/folie-15_med.png)

Insertion of values into the Java class template is performed in the same way as in the letter template example. 
The type of model from which the data is obtained to be inserted into the template beans is totally arbitrary.

All features are described in the [tutorial and handbook...](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework)

## Tutorial & Handbook
Click here for the [Slideshare presentation](http://de.slideshare.net/Robert_Mencl/jiowa-code-generator-framework)
and here for the 
[PDF version of the handbook](http://www.jiowa.de/jiowa-codegen/doc/Jiowa-Code-Generation-Tutorial_and_Handbook-2.1.pdf).

## Download

The distribution consists of a Maven project with an example for a code generation application, generator templates, and the [PDF version of the Tutorial & Handbook](http://www.jiowa.de/jiowa-codegen/doc/Jiowa-Code-Generation-Tutorial_and_Handbook-2.1.pdf). 
The project has been slightly optimized for Eclipse IDE so that the template beans are automatically re-generated if a template or its properties change. For IntelliJ IDEA and Netbeans IDE you will have to hit the re-build button. 

[**Download the code generation framework here ...**](http://www.jiowa.de/download.html)

You might also want to have a look at the [README](http://www.jiowa.de/jiowa-codegen/README) file of the distribution.

Java Doc: [www.jiowa.de/jiowa-codegen/doc/api/](http://www.jiowa.de/jiowa-codegen/doc/api/)

##License
JIOWA Code Generation Framework is licensed under the 
[JIOWA Backlinking License 1.0](http://www.jiowa.de/jiowa-codegen-license.html)
which basically means the following.

**JIOWA Code Generation Framework**

is free for commercial and non-commercial use under the following conditions: 

* you set a public link from your website(s) to www.jiowa.de stating that you use the JIOWA Code Generation Framework. 
  If you do not own a website then you can set a public backlink from your favourite social media account to www.jiowa.de.
  Example link text: ["We are using the JIOWA Code Generation Framework!"](http://www.jiowa.de)

* and you leave all our copyright/license notices inside the distribution.

[Full license text is here](http://www.jiowa.de/jiowa-codegen-license.html).
