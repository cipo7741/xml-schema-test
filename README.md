# XML-Schema Test

XML-Namespaces: Probe auf's Exempel mit [http://www.xmlvalidation.com](http://www.xmlvalidation.com)

## Fragen, die dieses Repo beantworten will

1. Ignoriert `noNamespaceSchemaLocation` den `targetNamespace` vom Schema?
  - Nein, es darf kein `targetNamespace` im Schema stehen, wenn im Instanzdokument `noNamespaceSchemaLocation` genutzt wird.
  - Errors in the XML-Document: Cannot find the declaration of element 'person'.
  - Errors in file XML-Schema: Expecting no namespace, but the schema document has a target namespace of `http://www.buw.de/webtec`.

2. Kann man durch die URI in der `schemaLocation` den `targetNamespace` des Schemas überschreiben?
  - Errors in file [https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd](https://raw.githubusercontent.com/cipo7741/xml-schema-test/master/webis-person.xsd)
TargetNamespace.1: Expecting namespace `http://www.buw.de/databases`, but the target namespace of the schema document is `http://www.buw.de/webtec`.
  - Nein, man kann nicht durch die URI in der `schemaLocation` den `targetNamespace` des Schemas überschreiben.

3. Wofür wird das Attribut `schemaLocation` gebraucht?
  - Der Java-XML-Parser läd das Schema, dass in `schemaLocation` oder `noNamespaceSchemaLocation` angegeben ist um ein Instanzdokument zu validieren.
  - Mache Java-Biblotheken verweisen intern zu einer URL auf ein Schema, so das der Parser kein Schema runterladen muss
  - Quelle: [http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation](http://stackoverflow.com/questions/5875021/what-is-the-use-of-xsischemalocation)

4. Muss die URI in der `schemaLocation` angeben werden?
  - Ohne URI nutzt man das Attribut `noNamespaceSchemaLocation`.

5. Wenn im Schema kein `targetNamespace` angeben ist, sind die Elemente des Schemas dann im **default Namensraum** oder im **anonymen Namensraum**?
  - Da man keinen Namensraum vergiebt, haben die Elemente des Schemas keinen Namensraum (das könnte man **anonymen Namensraum** nennen). Sie sind nicht im **default Namensraum**.
