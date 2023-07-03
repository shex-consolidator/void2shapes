# void2shapes

This repository contains SPARQL CONSTRUCT queries that generate [ShEx](http://shex.io/) and [SHACL](https://www.w3.org/TR/shacl/) shapes from [Void](https://www.w3.org/TR/void/) 
 description files for Uniprot.

These examples have been created by Jerven Bolleman & Jose Emilio Labra at Biohackathon 2023

# Requirements

The steps require Apache Jena to be installed.

# Obtaining void descriptions

Swiss lipids is a smaller example. 

```sh
curl -H 'accept:application/rdf+xml' 'https://beta.sparql.swisslipids.org/' > void/swisslipids-void.rdf
```

```sh
curl -H 'accept:application/rdf+xml' 'https://sparql.uniprot.org/' > void/uniprot-void.rdf
```


## SHACL generation 

```sh
sparql --data=void/uniprot-void.rdf --query=sparql/uniprot-void-shacl.sparql > generated/shacl/uniprot-shacl.ttl
```

## ShEx generation 

```
sparql --data=void/uniprot-void.rdf --query=sparql/uniprot-void-shex.sparql > generated/shex/uniprot-shex.ttl
```
