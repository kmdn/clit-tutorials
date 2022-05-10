0. Run the combining linking techniques (CLiT) framework.
1. Access the combining linking techniques (CLiT) front-end interface. E.g. open http://localhost:8080 (may depend on your configuration) in your browser.
2. Press "Add Complex Linker Pipeline".
3. For each node appearing, click on it and press "DEL" until only the nodes "Input" and "Output" are left.
4. On the right side of the graph visualization, click "Add component".
Choose "Mention Detector".
5. Click on the newly-created node.
6. On the right-hand side, click on the dropdown box button and choose which supported 
mention detector you would like to execute (e.g. DBpediaSpotlight).
Note: If you choose an IP-based component, you need to add the IP address it may be accessed at through CLiT's defined protocols in the textfield below.
7. Define the information flow by setting which is given the input text and which component should output its results.
	1. Sources: Click on the button and select the "input" node as a source.
	2. Targets: Click on the button and select the "output" node as a target.
8. Run the experiment by pressing "Run Experiment". A new tab with results should open in your browser.
