# How to store and display intermediary results of pipeline components.
0. Run the combining linking techniques (CLiT) framework.
1. Access the combining linking techniques (CLiT) front-end interface. E.g. open http://localhost:8080 (may depend on your configuration) in your browser.
2. Press "Add Complex Linker Pipeline".
3. Setup a desired pipeline configuration. 
	1. Add wanted components by clicking on "Add Component" and selecting which types of components you would like (e.g. DBpediaSpotlight for mention detection and Opentapioca for combined candidate generation & entity disambiguation).
	2. Connect components depending on desired information flow starting from the "Input" text node and leading to the "Output" result node. This may be done by clicking on a component's node, selecting its "Sources" (= incoming information) and defining its connectivity. 
	Analoguously, one should define "Targets", determining which other components receive information from a given component.
		1. Sources: Click on the button and select the wanted node as a source.
		2. Targets: Click on the button and select the "Output" node as a target if you want it to be displayed.
4. For each node whose output should be tracked in the final results, add a connection from its respective node to the "Output" node. This ensures intermediary pipeline results to be explicitly stored in the output document.
5. Run the experiment by pressing "Run Experiment". A new tab with results should open in your browser.
