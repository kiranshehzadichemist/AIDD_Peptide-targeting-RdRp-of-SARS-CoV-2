# AIDD_Peptide-targeting-RdRp-of-SARS-CoV-2
This repository contains complete AI codes, input and output data for design of short peptides, targeting RdRp of SARS-CoV-2 
The workflow includes:
1. Protein_Protein_and_Protein_Peptide_complexes_retrieved_from_RCSB:
In 1st step we use code to queries the RCSB PDB database to fetch protein-peptide and protein-protein complex structures using advanced search parameters, then outputs the unique PDB IDs
2. Data preprocessing of amino acid interactions:
This code predicts the interaction probability between two amino acids by encoding their residue types
3. Clean and preprocesses raw amino acid interaction data:
This code cleans and preprocesses raw amino acid interaction data by extracting standardized 3-letter residue codes from input strings while filtering out invalid or unprocessable entries.
4. Prediction of amino acid interaction probabilities:
This code trains a Random Forest classifier to predict amino acid interaction probabilities using encoded residue pairs and their distances, evaluates its accuracy, and saves the model for deployment.
Key Components:
RandomForestClassifier: Ensemble ML algorithm using 100 decision trees
train_test_split: Creates 80/20 training/testing split
joblib: Saves trained model to disk (.pkl format)
Input features: Encoded amino acids (AA1_encoded, AA2_encoded) + distance (AvgDistance)
Target: Binary interaction labels (Interaction)

5.	Random Forest model training:
The code is doing:
 Matrix generation (affinity and distance),
 Creating a dataset for ML (with positive and negative samples),
 Encoding the amino acids for ML,
 Defining a function to predict top inhibitor residues for input sequences.

6.	Prerequisites
- Python 3.7+
- Required libraries:
  ```bash
  pandas, numpy, scikit-learn, joblib

7.	Install with:
pip install pandas, numpy, scikit-learn, joblib
