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

* for entity disambiguation:
	* Radboud Entity Linker (REL)

Despite our supported list containing a wide choice of components, this framework still offers another possibility of intergrating *your* components, giving you complete control over the pipeline.
To easily do so, there is a very simple template script for each component type. These provide a simple web service, comunicating with the framework's backend, to provide the output of the pipeline's component.
Here is a sketch illustrating the idea behind this:

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
                        |    localhost:5001    |                  |                           |   localhost:5003  +-+
                        |                      +------------------+                           |                   |
                        +----------------------+                                              +-------------------+

