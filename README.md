# XInclude 1.1 Attribute Copy and xml:id Fixup Example

This example illustrates certain features of xinclude 1.1:

1. If you add `set-xml-id` on an xi:include element, the value of `set-xml-id` overwrites the xml:id on the included element.
2. If you add an attribute in the namespace `http://www.w3.org/2001/XInclude/local-attributes` on xi:include, that attribute is passed down with no namespace prefix.
3. If you add an attribute in any other namespace (except for the special xml: prefix), that attribute is passed down with its namespace. 

From what I can tell, Oxygen is doing 2 and 3, but not 1. 


