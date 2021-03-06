# kb-data-extracts

Queries (primarily in [SPARQL]) for data extracts, summaries, reports, etc from the RDF graph in the Phenoscape Knowledgebase (KB).

## Submitting queries

[SPARQL] queries can be submitted from the command line using `curl`:


    $ curl -X POST --data-binary @search_character_descriptions.rq \
                   --header "Content-Type: application/sparql-query" \
                   --header "Accept: text/tab-separated-values" \
                   http://localhost:8080/bigdata/sparql > result.txt
  
You will need to replace the endpoint URI (`http://localhost:8080/bigdata/sparql` in the command line example above) with the correct location of the SPARQL service.

You can also interactively enter the query and modify it iteratively based on results, for example using [YASGUI]. (You will need to provide the SPARQL endpoint, see below.)

## Phenoscape KB SPARQL endpoint

The public SPARQL endpoint for the Phenoscape KB is currently at http://kb-dev.phenoscape.org/bigsparql. Note that dereferencing this URL will download the dataset descriptions (using [VoID]) in RDF format, the size of which is already significant (>50MB).

[SPARQL]: http://www.w3.org/TR/sparql11-overview/
[VoID]: https://www.w3.org/TR/void/
[YASGUI]: http://yasgui.org/
