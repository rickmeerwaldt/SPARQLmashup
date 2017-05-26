# SPARQLmashup

A framework on how to make a digital music mashup using the Semantic Web technology stack.

## What is a mashup
A mashup is a song or composition created by blending two or more pre-recorded songs (https://en.wikipedia.org/wiki/Mashup_(music)).

## The framework
A framework was contructed as result of research on the subject of the possibilities of making digital music mashups concretely by means of SPARQL queries on MIDI Linked Data (see https://midi-ld.github.io)

See FRAMEWORK.png for a very preliminary version of the framework
- all required queries can be found in queries.pdf

### Query for the mashup
A query is constructed to be used on the MIDI Linked Data SPARQL endpoint (see http://virtuoso-midi.amp.ops.labs.vu.nl/sparql) in order to generate a MIDI Linked Data mashup. 

### More queries
But before the final query can be made, the MIDI Linked Data cloud needs to be explored in order to find
- two songs with the same tempo
- tracks from those songs that are going to be used in the mashup

See queries.pdf for all queries that are required for making a mashup 

## Making a mashup by means of an example
For a step by step generation of a MIDI Linked Data mashup see example

## Changelog

26-05-2017:
- Added the example map with the according file
- Added new version of the framework, frameworkV2


