CEO method works only with object properties assertions and can't work with data property assertions. This creates a constraint on which ontologies may be used. 

Criterias:
- object properties should be used in constructing a taxonomy
- data properties should be used as little as possible


Found ontologies:

|Name | URL | Status | Size | Suitable |
|--|--|--|--|--|
| Koala | - | Contains suitable rules but relies on data properties | 70 | No |
| Food & Wine | - | Does not contain data properties | 1223 | Yes |
| Instruments | - | Does not contain data properties | 299 | Yes |
| Pizza | - | - | - | - |
| Homology | [link](http://purl.obolibrary.org/obo/hom.owl)) | Does not contain object or data properties| 565 | No |
| Plants | [link](https://raw.githubusercontent.com/Planteome/plant-ontology/v2021-08-13/po.owl) | Contains object properties, does not contain data properties | 24,532 | Maybe |
| Uberon | [link](http://purl.obolibrary.org/obo/uberon.owl) | Quite complex, contains object properties, does not contain data properties | 370,000+ | Most probably no |
| Duo | [link](https://raw.githubusercontent.com/EBISPOT/DUO/master/duo.owl) | Contains object properties and numerical data properties | 4,300 | Maybe but cautiously |
| IAO | [link](https://raw.githubusercontent.com/information-artifact-ontology/IAO/v2022-11-07/iao.owl) | Have similar structure as DUO | 3,718 | Maybe but with cautiously |
| STATO | [link](http://purl.obolibrary.org/obo/stato.owl) | Have similar structure as DUO | 11,674 | Maybe but with cautiously |
