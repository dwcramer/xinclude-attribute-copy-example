# XInclude 1.1 Attribute Copy and xml:id Fixup Example

This example illustrates certain features of xinclude 1.1:

* doc.xml is the parent, including file.
* src.xml is the child, included file.
* doc-xincluded-calabash.xml is the result of processing doc.xml with xmlcalabash performing the xinclude.
* doc-xincluded-oxygen.xml is the result of processing doc.xml with Oxygen and an identity transform.

Expected result based on this version of the spec:

* https://www.w3.org/TR/xinclude-11/#attribute-copying
* https://www.w3.org/TR/xinclude-11/#att-copy-example

1. If you add `set-xml-id` on an xi:include element, the value of `set-xml-id` overwrites the xml:id on the included element.
2. Attributes in the special xml: namespace are not copied down and have no effect. 
3. If you add an attribute in the namespace `http://www.w3.org/2001/XInclude/local-attributes` on xi:include, that attribute is passed down with no namespace prefix.
4. If you add an attribute in any other namespace (except for the special xml: prefix), that attribute is passed down with its namespace. 
5. If you add an attribute not in any namespace to an xi:include it will not be passed down and, aside from `set-xml-id`, will have no effect. 

From what I can tell, Oxygen is doing 3, 4, and 5, but not 1 and 2. Calabash is doing all four. 

In the case of 2, Oxygen is replacing the xml:id on the included content.

This leaves open what to do about xml:ids that are nested inside included content. 