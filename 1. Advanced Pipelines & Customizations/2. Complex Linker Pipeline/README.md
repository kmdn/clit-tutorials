# How to create and run a complex linker pipeline.
0. Run the combining linking techniques (CLiT) framework.
1. Access the combining linking techniques (CLiT) front-end interface. E.g. open http://localhost:8080 (may depend on your configuration) in your browser.
2. Press "Add Complex Linker Pipeline".
3. Ideology: 
	1. Each node is a component of some kind. "Input" and "Output" nodes refer to where documents are fed in and which components should have their results output.
	2. A linker generally consists of 
		1. Mention Detection: Takes plain text and creates mentions (spans) it outputs.
		2. Candidate Generation: Takes mentions and generates a variety of candidate entities it may refer to as an output.
		3. Entity Disambiguation: Takes a variety of candidate entities and determines a ranking of entities (or a single entity, if any) for every mention.
	3. We introduced the following conceptual components:
		1. Splitter: "Splits" results from one component to multiple succeeding components (may be done in smart fashions, by default all results are passed as-is).
		2. Combiner: Represents the opposite operation of splitting by combining results from multiple preceding components into a single merged output (e.g. by making an intersection or union operation on various levels).
		3. Translator: Allows for 'translating' an entity (=IRI related to a specific knowledge base) to another knowledge base - allowing system interoperability (e.g. to allow usage of DBpedia and Wikidata simultaneously).
		4. Filter: Allows 'filtering' of information through use of specific rules (e.g. to only allow rdf:type Person entities to be annotated).
4. Add a component & define interactions
	1. On the right side of the graph visualization, click "Add component".
	2. Click on the newly-created node.
	3. On the right-hand side, click on the dropdown box button and choose which supported 
	component you would like to execute (e.g. mention detector based on DBpediaSpotlight).
	Note: If you choose an IP-based component, you need to add the IP address it may be accessed at through CLiT's defined protocols in the textfield below.
	4. Define the information flow by setting which component is given the input text and which component should output its results, as well as their connectivities among each other.
		1. Sources: Click on the button and select desired preceding node(s) as source(s).
		2. Targets: Click on the button and select desired succeeding node(s) as target(s).
5. *If* the pipeline was correctly created, you may run the experiment by pressing "Run Experiment". A new tab with results should open in your browser.
