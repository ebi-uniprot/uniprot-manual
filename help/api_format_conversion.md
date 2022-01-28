
---
title: Programmatic access - Format conversion
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Technical,help
---

This service allows you to convert data between different formats. Note that at the moment only single entries are supported. Here is a [Java example](http://www.uniprot.org/help/api_format_conversion#conversion_java_example) (using the [Jakarta Commons HttpClient](http://jakarta.apache.org/commons/httpclient/) library) to convert a UniProtKB entry from `txt` to `rdf` format.

PostMethod method = new PostMethod("https://www.uniprot.org/convert");
Part\[\] parts =
{
  new StringPart("type", "uniprot"),
  new StringPart("from", "txt"),
  new StringPart("to", "rdf"),
  new FilePart("data", new File("P05067.txt"))
};
method.setRequestEntity(new MultipartRequestEntity(parts, method.getParams()));
HttpClient client = new HttpClient();
String contact = ""; // Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
client.setRequestHeader("User-Agent", "Java " + contact);
int status = client.executeMethod(method);
if (status != HttpStatus.SC\_OK)
  println(method.getStatusLine());
else
  println(method.getResponseBodyAsString());

See also:

[REST API - Access the UniProt website programmatically](http://www.uniprot.org/help/api) - batch retrieval, ID mapping, queries, downloads, etc

Related terms: programmatic access, program, script, wget, curl, web services, API
        