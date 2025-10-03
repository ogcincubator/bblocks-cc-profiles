
# Simple JSON properties for CC TASLAR profile (Schema)

`ogc.profiles.cc.tasl-json` *v0.1*

A set of properties that can be added to any object enforcing TASLAR 

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### A simple Collection demonstrating Themes extension fields in a Collection.
#### json
```json
{  "id": "urn:mything",
   "title" : "A title",
   "author": "orcid:2002-11-22-33",
   "source": "some text?",
   "licence": "cc:ccby4"
}
```

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-cc-profiles/build/annotated/profiles/cc/tasl-json/context.jsonld",
  "id": "urn:mything",
  "title": "A title",
  "author": "orcid:2002-11-22-33",
  "source": "some text?",
  "licence": "cc:ccby4"
}
```

#### ttl
```ttl
@prefix dct: <http://purl.org/dc/terms/> .

[] dct:author "orcid:2002-11-22-33" ;
    dct:title "A title" .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: CC TASL Extension
description: STAC extension for the Creative Commons TASLAR attibution profile.
properties:
  title:
    type: string
    x-jsonld-container: '@set'
    x-jsonld-id: http://purl.org/dc/terms/title
  author:
    $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/ogc-utils/iri-or-curie/schema.yaml
    x-jsonld-id: http://purl.org/dc/terms/author
  license:
    $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/ogc-utils/iri-or-curie/schema.yaml
    x-jsonld-id: dcat:license
  source:
    type: string
x-jsonld-prefixes:
  dct: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-cc-profiles/build/annotated/profiles/cc/tasl-json/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-cc-profiles/build/annotated/profiles/cc/tasl-json/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "title": {
      "@container": "@set",
      "@id": "dct:title"
    },
    "author": "dct:author",
    "license": "dcat:license",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-cc-profiles/build/annotated/profiles/cc/tasl-json/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-cc-profiles](https://github.com/ogcincubator/bblocks-cc-profiles)
* Path: `_sources/tasl-json`

