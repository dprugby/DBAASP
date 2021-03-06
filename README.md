# Predictive modeling for antimicrobial peptides 

This repository implements various machine learning algorithms for classifying peptides as active or non-active against gram-positive bacteria Staphylococcus aureus - a problem, generally relevant for antibiotic discovery in medicine. 

For non-biologists/biophysicists (like me), mostly oriented towards the machine learning side of the problem, a short summary of the exercise follows. 

Peptides are sequences, consisting of amino acids - small molecules, coming in a variety of a couple of dozen kinds. Different amino acids are characterized by different physical and chemical properties and are usually coded by capital Latin letters, so that e.g. the peptide known as Distinctin would be represented as 'NLVSGLIEARKYLEQLHRKLKNCKV'. Using the laws of biophysics, out of every such sequence one can extract twelve numeric characteristics of the given peptide. These twelve numbers serve as features for our classification task. Their names, together with their respective data types, are:

1. Normalized Hydrophobic Moment (float64)
1. Normalized Hydrophobicity (float64)                     
1. Net Charge (int64)                                      
1. Isoelectric Point (float64)                              
1. Penetration Depth (int64)                               
1. Tilt Angle (int64)                                         
1. Propensity to Disordering (int64)                         
1. Linear Moment (float64)                                    
1. Propensity to in vitro Aggregation (float64)               
1. Angle Subtended by the Hydrophobic Residues (int64)       
1. Amphiphilicity Index (float64)                            
1. Propensity to Coil Conformation (float64)   

![Image](https://github.com/dprugby/DBAASP/blob/master/img.png?raw=true)

There are 424 instances of peptides in the dataset, labeled by the target variable 'Class' that takes on values 0 or 1, depending on whether the given peptide is (respectively) active or non-active against Staphylococcus aureus. For all 424 instances, the target variable represents an expensive experimental measurement, hence the relative smallness of the dataset. 

We try a wide spectrum of standard machine learning algorithms for classifying peptides into the two possible classes, and find that random forests and a shallow (regularized) feedforward neural network perform best (both in terms of the overall accuracy, as well as in terms of precision and recall).

The data used in the present analysis is publicly available from the [Database of Antimicrobial Activity and Structure of Peptides](https://dbaasp.org/), or DBAASP for short.
