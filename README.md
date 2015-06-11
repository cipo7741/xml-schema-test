# XML-Schema Test

### Fragen, die dieses Repo beantworten will

1. Ignoriert NoNamespaceSchemaLocation den TargetNamespace vom Schema?
2. Kann man durch die URI in der `schemaLocation` den `targetNamespace` des Schemas überschreiben?
**Nein**
[http://www.xmlvalidation.com](http://www.xmlvalidation.com)

Errors in file [https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd](https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd)
TargetNamespace.1: Expecting namespace `http://www.buw.de/databases`, but the target namespace of the schema document is `http://www.buw.de/webtec`.

Wofür brauch man dann das Attribut `schemaLocation`?
[http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation](http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation)

3. Muss man die URI in der `schemaLocation` angeben?
4. Wenn ich im Schema kein `targetNamespace` angebe, sind die Elemente des Schemas im **defaultNamensraum** oder im **anonymen Namensraum**?
