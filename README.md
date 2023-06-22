# Combining Linking Techniques tutorials
This is the GitHub repository for tutorials regarding the Combining Linking Techniques framework.

Here you will find Jupyter notebooks, tutorials, guides, a user study experiment incl. results and more!

The main project may be found here: [Combining Linking Techniques](https://github.com/kmdn/combining-linking-techniques "Combining Linking Techniques (CLiT)")

## Folder structure explanations:
### ./**0. Simple Pipelines & default usage**
Textual step-by-step guide on our system basics and on how to run available entity linking systems and parts thereof.
### ./**1. Advanced Pipelines**
Textual step-by-step guide on how to display intermediary results or set up so-called complex pipelines.
### ./**2. Use Own Pipeline Components**
*This is where it's at.*
Here you will find Jupyter Notebooks for each possible type of component on how to allow **your own** component to run with ours.
You will require to know how to access your own system's entrypoint, but we try to help you through the process of mapping our framework's information to your own!
This way, our framework will connect via our provided API templates and communicate with your component (linker) when configured on the front-end demonstrator (or in your request to the API).

Jupyter Notebooks currently exist for the following components, among others: 
1. mention detection (MD)
2. candidate generation (CG) 
3. entity disambiguation (ED)
4. splitter (SP)
5. combiner (CO)
6. translator (TR)
7. filter (FI).

### ./**User Study Experiment**
Contains a user study experiment.





