# SPARQLmashup


A preliminary tutorial on how to make a digital music mashup using the Semantic Web technology stack.

# The framework
A framework was contructed as result of research on the subject of the possibilities of making digital music mashups concretely by means of SPARQL queries on MIDI Linked Data (see https://midi-ld.github.io)

See FRAMEWORK.png for a very preliminary version of the framework

# Query
The following query was constructed to be used on the MIDI Linked Data SPARQL endpoint (see http://virtuoso-midi.amp.ops.labs.vu.nl/sparql) in order to generate a MIDI Linked Data mashup:

<pre>
PREFIX prov: <http://www.w3.org/ns/prov#> 
PREFIX mid: <http://purl.org/midi-ld/midi#>

CONSTRUCT { <newsong> a mid:Pattern ;
mid:hasTrack ?track . 
<newsong> mid:format ?format .
?track mid:hasEvent ?event .
?track a mid:Track .
?event a ?type .
?event ?property ?value .
}

WHERE { 
{
?pattern prov:wasDerivedFrom ?filename .
?pattern mid:hasTrack ?track .
?pattern mid:format ?format .
?pattern mid:resolution ?resolution .
?track mid:hasEvent ?event .
?event a ?type .
?event ?property ?value .
FILTER (regex(?filename, "song1", "i")) .
FILTER (?track IN (<track1>, <track2>, <and so on>))
} UNION {
?pattern prov:wasDerivedFrom ?filename .
?pattern mid:hasTrack ?track .
?pattern mid:format ?format .
?pattern mid:resolution ?resolution .
?track mid:hasEvent ?event .
?event a ?type .
?event ?property ?value .
FILTER (regex(?filename, "song2", "i")) .
FILTER (?track IN (<track1>, <track2>, <and so on>))
}
}
</pre> 

# Explanation of the framework

# Making a mashup by means of an example
A step by step generation of a mashup
