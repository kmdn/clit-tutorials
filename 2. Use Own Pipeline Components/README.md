# Integrate own pipeline components
This framework allows its users to use a set of readily available pipeline components:
* for mention detection:
    * AIDA
    * Babelify
    * DBpediaSpotlight
    * EntityClassifierEULinker
    * FOX
    * Falcon 2.0
    * OpenTapioca
    * REL
    * TagMe
    * TextRazor
    * spaCy
 
* for candidate generation:
    * DBpediaLookup
    * WikidataDict

There are no default entity disambiguators for now, although REL is being worked on.  

Even though the list contains a wide choice of components, maybe not so for entity disambiguators due to the lack of services that offer that part of the pipeline, this framework still offers another possibility to intergrate own components, which gives the users a complete control over the pipeline.
To be able to easily do so, and for each component there is a very simple template script, that provides a web service, which then will comunicate with the framework's backend, to provide the output of the pipeline's component.
Here is a sketch of the idea behind this:

    +-----------------------------------------------------------------------------------------------------------------+
    |                                                                                                                 |
    |                                                      +--------------+                                           |
    |                                                      |              |                                           |
    |                                                      | WikidataDict +-------------------------+                 |
    |                                                      |              |                         |                 |
    |                                                      +--------------+                         |                 |
    |                                                             ^                                 |                 |
    |                                                             |                                 |                 |
    |                                                             |                                 |                 |
    | +-----------+      +-------------------+        +-----------+-----------+        +------------v-----------+     |
    | |           |      |                   |        |                       |        |                        |     |
    | |   Input   +------> Mention Detection |        |  Candidate Generator  |        |   Entity Disambiguator |   +-->
    | |           |      |                   |        |                       |        |                        |   | |
    | +-----------+      +---------+---------+        +-----------^-----------+        +--------------+---------+   | |
    |                              |                              |                                   |             | |
    |                              |                              |                                   |             | |
    +------------------------------+------------------------------+-----------------------------------+-------------+-+
                                   |                              |                                   |             |
                                   |                              |                                   |             |
                                   |                              |                                   |             |
                        +----------v-----------+                  |                           +-------v-----------+ |
                        |                      |                  |                           |                   | |
                        |    Own MD            |                  |                           |   Own ED          | |
                        |                      |                  |                           |                   | |
                        |    localhost:3001    |                  |                           |   localhost:3003  +-+
                        |                      +------------------+                           |                   |
                        +----------------------+                                              +-------------------+

