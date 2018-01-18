# Inferencing Stacks
Here is a list of technology stacks that can be used to perform inferencing on RDF graphs. The items in the list are collections that we have tested to ensure they work together.

| Name | Languages | Storage | Manipulation | Reasoner | Display | Requirements to use it | Status |
|-|-|-|-|-|-|-|-|
|Rdflib for python 2|Python 2.7|Memory  +SPARQL endpoint|[rdflib 2.*](https://rdflib.readthedocs.io/en/stable/) |[OWL-RL](https://github.com/RDFLib/OWL-RL)|||Untested,  working as of 2012|
|Rdflib for python 3|Python 3.6|Memory  +SPARQL endpoint|[rdflib 4.2.2](https://rdflib.readthedocs.io/en/stable/) |[OWL-RL >4 needs modification to upgrade it to use python 3](https://github.com/RDFLib/OWL-RL)|||Untested|
|[Apache Jena Fuseki 3.4.0](https://jena.apache.org/download/)|Accessed through web browser or command line tools|TDB or Memory|Jena 3.4.0 (included)|Any one of [Openllet 2.6.2](https://github.com/Galigator/openllet), or Jena Rules, or Owl Inferencing|[Fuseki 2](https://jena.apache.org/documentation/fuseki2/)|openllet-distribution-2.6.2.jar is required if want to use/have relativesWithOwlInferencingAndOpenlletReasoner configuration file|The following works. Query One: relativesWithOwlInferencingAndOpenlletReasoner, relatives-usingJenaRules, relativesWithOwlInferencing. Query Two: relativesWithOwlInferencingAndOpenlletReasoner, relatives-usingJenaRules. relativesWithOwlInferencing for Query Two does not give any results. This suggests that relativesWithOwlInferencingAndOpenlletReasoner and relatives-usingJenaRules is a fully functioning reasoning system but that relativesWithOwlInferencing is not.|
|DLEJena 1.0 (emailed to us)|Java|Memory|[Jena 2.6.4](http://jena.apache.org/download/index.cgi)|Pellet 2.3.6||Does not work using single jar generated using IntelliJ from DLEJena1 Maven Project. Does not work using multiple jars (maven-dependency-plugin) or single jar (maven-assembly-plugin) generated from DLEJena 1.0 Maven Project using [Apache Maven](http://maven.apache.org/)|Does not work|
|[DLEJena 2.0](http://lpis.csd.auth.gr/systems/DLEJena/index.html)|Java|Memory|[Jena 2.6.2](http://jena.apache.org/download/index.cgi)|Pellet 2.0.1||Works for the examples as well as sparql query 1 and query 2, using the following jars (for DLEJena V2): [owlapi-bin.jar](https://github.com/severin-lemaignan/pellet/blob/master/lib/owlapi/owlapi-bin.jar), [DLEJena.jar](http://lpis.csd.auth.gr/systems/DLEJena/index.html), [Jena-2.6.2 jars](https://sourceforge.net/projects/jena/files/Archive/Jena/Jena-2.6.2/jena-2.6.2.zip/download),[owlapi-bin-07-06-09 jars](https://sourceforge.net/projects/owlapi/files/OWL%20API%20%28for%20OWL%202.0%29/2.0.0/owlapi-bin-07-06-09.zip/download),  [pellet-2.0.1 jars](https://web.archive.org/web/20110813164347if_/http://clarkparsia.com/pellet/downloads/pellet-2.0.1.zip)|Works for both query one and two|
|[Openllet 2.6.2](https://github.com/Galigator/openllet)|Java|Memory|[Jena 3.4.0](http://jena.apache.org/download/index.cgi)|Openllet 2.6.2||Does not work using Intellij generated single jar. [Apache Maven](http://maven.apache.org/): Working with examples and sparql query 1 and query 2: output_ApacheMavenMultipleJars (made using maven-dependency-plugin). Not working: output_ApacheMavenSingleJar (made using maven-assembly-plugin)|Works for both query one and two|
|[Openllet 2.6.3 on github Galigator](https://github.com/Galigator/openllet)|Java|Memory|[Jena](http://jena.apache.org/download/index.cgi)|Openllet 2.6.3||[Apache Maven](http://maven.apache.org/): The pom.xml file in the examples folder does not compile using the maven-dependency-plugin (multiple jars) and maven-assembly-plugin (single jar), you can see the output it gives in _github\ Openllet,DLEJena2\ openllet maven\ openllet-2.6.3\ examples\ runApacheMaven-output.txt. Therefore nothing works.|Does not work|
|[Openllet 2.6.3 on mvnrepository](https://mvnrepository.com/artifact/com.github.galigator.openllet/openllet-examples/2.6.3)|Java|Memory|[Jena 3.4.0](http://jena.apache.org/download/index.cgi)|Openllet 2.6.3||[Apache Maven](http://maven.apache.org/): Working with examples and sparql query 1 and query 2: output_ApacheMaven_openllet2.6.3_mvnrepository_MultipleJars (made using maven-dependency-plugin). Not working: output_ApacheMaven_openllet2.6.3_mvnrepository_SingleJar (made using maven-assembly-plugin). Not all the examples are working but sparql including query 1 and query 2 work: output_manualJarChoice (openllet 2.6.3), which uses the jars  [apache-jena-3.4.0.zip](http://jena.apache.org/download/index.cgi) [openllet-distribution-2.6.3.jar](https://github.com/Galigator/openllet/releases) [owlapi-distribution-4.1.4.jar](https://sourceforge.net/projects/owlapi/files/OWL%20API%20%28for%20OWL%202.0%29/4.1.4/)|Works for both query one and two|
|[Rdflib.js](https://github.com/linkeddata/rdflib.js/releases)|Javascript|Memory|rdflib 0.16.3||HTML rendered in a browser such as FireFox||Does sparql but not inferencing|
|[Python Graphite](https://code.google.com/archive/p/python-graphite/)|[Python 2.6](https://www.python.org/downloads/) and Java|Memory|Jena 2.6.4 (integrated/ included)|[Openllet](https://github.com/Galigator/openllet)||[JPype 0.5.4.2](https://sourceforge.net/projects/jpype/)|Does sparql but not inferencing|
|[EasyRDF](http://www.easyrdf.org/)|PHP 5/7||EasyRDF||||Not tested|
|[PHP Graphite](http://graphite.ecs.soton.ac.uk/)|PHP||Graphite||||Not tested|
|.NET|||dotNetRDF|||||
|Ruby||||||||
|RDF4J (Sesame)||||||||
|[Stardog](https://www.stardog.com/)|?|Stardog|Stardog|Stardog|?||Not tested|
|[Protege](protege.stanford.edu)||||||||
|[NG4J](http://wifo5-03.informatik.uni-mannheim.de/bizer/ng4j/) and on [Sourceforge](https://sourceforge.net/projects/ng4j/)|||Jena 2.6.2 (included)||||Working examples not yet created. Not working with inferencing|

### Tests done on the above inferencing Stacks

The following (Query One and Query Two) used either relatives.ttl or relatives.owl which should both be equivalent. The "id" first column in each results table, which is the row number, that I have listed in both results below, is not actually in the results, I have just added it so that it is easily possible to identify each row.

#### Sparql Query One - hasChild Query

    PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
    PREFIX : <http://example.org/relatives#>

    SELECT *
    WHERE
    {
      ?s :hasChild ?o .
    }

Results:

Total 11 results - not necessarily in that order.

|id|s|o|
|-|-|-|
|1|```<http://example.org/relatives#John>```|```<http://example.org/relatives#Michael>```|
|2|```<http://example.org/relatives#John>```|```<http://example.org/relatives#Mary>```|
|3|```<http://example.org/relatives#Simon>```|```<http://example.org/relatives#Tim>```|
|4|```<http://example.org/relatives#Bill>```|```<http://example.org/relatives#Bob>```|
|5|```<http://example.org/relatives#Bill>```|```<http://example.org/relatives#Cathy>```|
|6|```<http://example.org/relatives#Cathy>```|```<http://example.org/relatives#Fred>```|
|7|```<http://example.org/relatives#Michael>```|```<http://example.org/relatives#Simon>```|
|8|```<http://example.org/relatives#James2>```|```<http://example.org/relatives#John>```|
|9|```<http://example.org/relatives#Fred>```|```<http://example.org/relatives#James>```|
|10|```<http://example.org/relatives#Fred>```|```<http://example.org/relatives#Jacob>```|
|11|```<http://example.org/relatives#Valerie>```|```<http://example.org/relatives#Tim>```|

#### Sparql Query Two - Grandparent Query

    PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
    PREFIX : <http://example.org/relatives#>

    SELECT ?gp
    WHERE
    {
      ?gc :hasGrandparent ?gp .
      ?gc a :Person .
    }

Results:

Total 7 results - not necessarily in that order.

|id|gp|
|-|-|
|1|```<http://example.org/relatives#Cathy>```|
|2|```<http://example.org/relatives#Cathy>```|
|3|```<http://example.org/relatives#Michael>```|
|4|```<http://example.org/relatives#John>```|
|5|```http://example.org/relatives#James2>```|
|6|```http://example.org/relatives#Bill>```|
|7|```<http://example.org/relatives#James2>```|

### Other reasoning tools
* S-Match
* WordNet

## Development Environments
Test edit

## Stack Server Installations


## Projects
* Digiscape
* AGISO
* EUDM
* PROMS
* Location Spine
