# SPARQLmashup

A framework on how to make a digital music mashup using the Semantic Web technology stack.

## What is a mashup
A mashup is a song or composition created by blending two or more pre-recorded songs (https://en.wikipedia.org/wiki/Mashup_(music)).

## The framework
A framework was contructed as result of research on the subject of the possibilities of making digital music mashups concretely by means of SPARQL queries on MIDI Linked Data (see https://midi-ld.github.io)


![alt text](https://github.com/rickmeerwaldt/SPARQLmashup/blob/master/Framework.png)
<i>all required queries can be found in queries.pdf</i>

### Query for the mashup
A query is constructed to be used on the MIDI Linked Data SPARQL endpoint (see http://virtuoso-midi.amp.ops.labs.vu.nl/sparql) in order to generate a MIDI Linked Data mashup. 

```SPARQL
PREFIX prov: <http://www.w3.org/ns/prov#> 
PREFIX mid: <http://purl.org/midi-ld/midi#>
CONSTRUCT { <pattern1> a mid:Pattern ; 
mid:hasTrack ?track .
<pattern1> mid:format ?format . 
<pattern1> mid:resolution ?resolution . 
?track mid:hasEvent ?event .
?track a mid:Track . ?event a ?type .
?event ?property ?value . }
WHERE {
<pattern1> mid:hasTrack ?track . 
<pattern1> mid:format ?format . 
<pattern1> mid:resolution ?resolution . 
?track mid:hasEvent ?event .
?event a ?type .
?event ?property ?value .
}
```


### More queries
But before the final query can be made, the MIDI Linked Data cloud needs to be explored in order to find
- two songs with the same tempo
- tracks from those songs that are going to be used in the mashup

<i>See queries.pdf for all queries that are required for making a mashup</i> 

## Making a mashup by means of an example
For a step by step generation of a MIDI Linked Data mashup see example

## Changelog

26-05-2017:
- Added the map: 'example' with the according files
- Added new version of the framework: 'frameworkV2'

04-06-2017:
- Replaced Queries.pdf with a new version (more use of URI's instead of FILTER)
- Replaced all the files in the example map (uses now the new version of Queries.pdf)

06-04-2017
- Small changes in Queries.pdf and Example.pdf (now also filter on resolution)



