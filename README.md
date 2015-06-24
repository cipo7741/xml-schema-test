# XML-Schema Test

## Fragen, die dieses Repo beantworten will

### Ignoriert `noNamespaceSchemaLocation` den TargetNamespace vom Schema?
  - Nein, es darf kein `targetNamespace` im Schema stehen, wenn im Instanzdokument `noNamespaceSchemaLocation` genutzt wird. 
### Kann man durch die URI in der `schemaLocation` den `targetNamespace` des Schemas überschreiben?
  - Probiert mit [http://www.xmlvalidation.com](http://www.xmlvalidation.com)
  - Errors in file [https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd](https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd)
TargetNamespace.1: Expecting namespace `http://www.buw.de/databases`, but the target namespace of the schema document is `http://www.buw.de/webtec`.
  - Nein, man kann nicht durch die URI in der `schemaLocation` den `targetNamespace` des Schemas überschreiben.

### Wofür brauch man dann das Attribut `schemaLocation`?
  - Der Java-XML-Parser läd das Schema, dass in `schemaLocation` oder `noNamespaceSchemaLocation` angegeben ist um ein Instanzdokument zu validieren.
  - Mache Java-Biblotheken verweisen intern zu einer URL auf ein Schema, so das der Parser kein Schema runterladen muss
  - Quelle: [http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation](http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation)
  
### Muss man die URI in der `schemaLocation` angeben?
  - Ohne URI nutzt man das Attribut `noNamespaceSchemaLocation`.

### Wenn ich im Schema kein `targetNamespace` angebe, sind die Elemente des Schemas im **default Namensraum** oder im **anonymen Namensraum**?
  - Da man keinen Namensraum vergiebt, haben die Elemente des Schemas keinen Namensraum (das könnte man **anonymen Namensraum** nennen). Sie sind nicht im **default Namensraum**.
