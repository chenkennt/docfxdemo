---
uid: System.Xml.Linq.XDocument
---

### Overview of the XDocument class

The @System.Xml.Linq.XDocument class contains the information necessary for a valid XML document.
This includes an XML declaration, processing instructions, and comments.

Note that you only have to create @System.Xml.Linq.XDocument objects if you require the specific functionality provided by the @System.Xml.Linq.XDocument class.
In many circumstances, you can work directly with @System.Xml.Linq.XElement.
Working directly with @System.Xml.Linq.XElement is a simpler programming model.

@System.Xml.Linq.XDocument derives from @"System.Xml.Linq.XContainer".
Therefore, it can contain child nodes.
However, @System.Xml.Linq.XDocument objects can have only one child @System.Xml.Linq.XElement node. This reflects the XML standard that there can be only one root element in an XML document.

### Components of XDocument

An @System.Xml.Linq.XDocument can contain the following elements:

- One @System.Xml.Linq.XDeclaration object. @System.Xml.Linq.XDeclaration enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.
- One @System.Xml.Linq.XElement object. This is the root node of the XML document.
- Any number of @System.Xml.Linq.XProcessingInstruction objects. A processing instruction communicates information to an application that processes the XML.
- Any number of @System.Xml.Linq.XComment objects. The comments will be siblings to the root element. The @System.Xml.Linq.XComment object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.
- One @System.Xml.Linq.XDocumentType for the DTD.

When you serialize an @System.Xml.Linq.XDocument, even if **XDocument.Declaration** is **null**, the output will have an XML declaration if the writer has **Writer.Settings.OmitXmlDeclaration** set to **false** (the default).

By default, LINQ to XML sets the version to "1.0", and sets the encoding to "utf-8".

### Using XElement without XDocument

As previously mentioned, the @System.Xml.Linq.XElement class is the main class in the LINQ to XML programming interface.
In many cases, your application will not require that you create a document.
By using the @System.Xml.Linq.XElement class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.

### Using XDocument

To construct an @System.Xml.Linq.XDocument, use functional construction, just like you do to construct @System.Xml.Linq.XElement objects.

The following code creates an @System.Xml.Linq.XDocument object and its associated contained objects.

[!code-cs[snippet1](sample.cs#snippet1)]
