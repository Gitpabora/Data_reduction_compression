# CCE AIML - learning data compression for Machine learning
### by  Shriti Singh , Parinita Bora
## The algorithms experimented with with high resolution image data  as a part of preprocessing of data  :SVD, PCA, K-mean 
 
For training a machine learning model When there is large amount of unlabeled data, unsupervised learning algorithms helps in undestanding data. Unsupervised learning also can help in dimensionality reduction. Dimensionality reduction again can help in data visualization (e.g. t-SNA method) When the data is reduced, the complexity of the model can be reduced, so as the traing time.
####  an example data file with dimention 570X 985 x 3 is an image of Cosmic object, Captured by James Webb Space Telescope (publicly available in Nasa wesite)                                                                                                                    
![sample image](data/sample_image.jpg) 

A brief note about the three unsupervised methods 

| Method                          | Inventor(s)                                                        | Purpose                            |
|--------------------------------  | ------------------------------------------------------------------ |-------------------------------------  | 
| Singular Value Decomposition(SVD) https://en.wikipedia.org/wiki/Singular_value_decomposition  | Independently Eugenio Beltrami, Camille Jordon over 100 yrs back   | To predict a set of optimal factors . |
| Principal comonent Analysis(PCA) https://en.wikipedia.org/wiki/Principal_component_analysis | Karl Pearson in 1901, later in 1930, developped by Harold Hotelling | Dimnetionality reduction          |
| K-Means clustering               | First used by James MacQueen in 1967 ,used by Steinhaus in 1956    | In pulse code modulation(by Steinhaus) |   





Advantages 
1. SVD : SDV simplifies data, can remove noise also it can be used for coloured image to segregation components for computational efficiency
2. PCA : Dimentionality reduction is the biggest advantage preserving most significant data. PCA can also used in data exploratory analysis and visualization
3. K-Mean : Simplicity and guerntees convergence 



## 1. PCA is commonly used  unsupervised dimensionality reduction method.
The data is projected onto its orthogonal subspace, that may help in reducing unwanted input data. 

<img align="right" src="https://upload.wikimedia.org/wikipedia/commons/f/f5/GaussianScatterPCA.svg" width="400">

In the figure the observations are in ellipsoid feature space.If the basis set vectors are orthogonal, highly correlated features can be removed, now the data  lies in a subspace having a smaller dimension.
This allows reduction of space with the newer projection. Each of the ellipsoid axes with maximal dispersion is choosen. 

### The steps in PCA mathematics 
Step 1.Calculate the covariance matrix of the data
step 2.Extract the eigenvectors and the eigenvalues of that matrix
Step 3. Select the number of desired dimensions and filter the eigenvectors to match it, sorting them by their associated eigenvalue
Step 4. Multiply the original space by the feature vector generated in the previous step.

The compression ratio is calculated for a experimented components :
new_number_of_values in the image matrix =570*components+985*components+components
compression ratio = ((original_number_of_values-new_number_of_values after applying PCA )/original_number_of_values)*100


| Algorithm                         | The detailed implementation  notepads |                                                       
|---------------------------------|----------------------------------------|
| PCA                             |  https://drive.google.com/file/d/1_pBJL6v9sRRetdD0tLqvmihOVvtvivf8/view?usp=share_link |
                     




### Experimental Results for  PCA


https://github.com/Gitpabora/Data_reduction_compression/tree/main/data/output


|components(Principal component)  |  compression ratio     |  Explained variance                        | Reconstructed Image           |    
|------------ | ------------- | -----------------------------------------|-------------------------------|
| 10          |  99.076202    | ![ev10](data/output/Explained_variance10.png) | ![rc10](data/output/reconstructed10.png ) | 
| 20          |  98.152403    | ![ev20](data/output/Explained_variance20.png)  | ![rc20](data/output/reconstructed20.png ) |
| 30          |  97.228605    | ![ev30](data/output/Explained_variance30.png)  | ![rc30](data/output/reconstructed30.png ) | 
| 40          |  96.304806    | ![ev40](data/output/Explained_variance40.png)  |![rc40](data/output/reconstructed40.png )  | 
| 50          |  95.381008    | ![ev50](data/output/Explained_variance50.png)  | ![rc50](data/output/reconstructed50.png ) | 
| 60          |  94.457209    | ![ev60](data/output/Explained_variance60.png)  | ![rc60](data/output/reconstructed60.png ) | 
| 70          |  93.533411    | ![ev70](data/output/Explained_variance70.png)  | ![rc70](data/output/reconstructed70.png ) | 
| 80          |  92.609612    | ![ev80](data/output/Explained_variance80.png)  | ![rc80](data/output/reconstructed80.png ) | 
| 90      |  91.685814    | ![ev90](data/output/Explained_variance90.png)    | ![rc90](data/output/reconstructed90.png ) |  
| 100         |  90.762015    | ![ev100](data/output/Explained_variance100.png) | ![rc100](data/output/reconstructed100.png ) |



## 2. SVD is a matrix factorization method where matrix (M) is  decomposed into three matrices (e.g. U, S, V)

The data is projected onto its orthogonal subspace, that may help in reducing unwanted input data. 


Algorithm
refernce:  https://iopscience.iop.org/article/10.1088/1757-899X/263/4/042082


### SVD Steps:
Step1.getting three component matrices with Red , Blue and green constituents
Step2. Applying SVD on each of the three components to generate three vectors for each of the matrices
Step3. Preserving only K  ie Selecting k columns from U matrix and k rows from VT matrix, and resetting rest to zero
Step4. Reconstructing the coloured components from U and V
Step5. Final image is formed by concatenating the three components 
Step5. Calculating the  the compression ratio= (original_Bytes-compressed_Bytes) / original_Bytes * 100


| Algorithm                         | The detailed implementation  notepads |                                                       
|---------------------------------|----------------------------------------|
| SVD                             |  https://colab.research.google.com/drive/1eG843MHVTwohPAqRmsQa8JToxPNJZR1M?usp=share_link |

### SVD copression ratio and recostruction
|components(k)  |  compression ratio     | Reconstructed image |   
|------------ | ------------------ |--------------------------|
| 10          |  97.23    | ![src10](data/output/sdv_rc10.png ) |
| 20          |  94.46    | ![src20](data/output/sdv_rc20.png ) |
| 30          |  91.69    | ![src30](data/output/sdv_rc30.png ) |
| 40          |  88.91    | ![src40](data/output/sdv_rc40.png ) |
| 50          |  86.14    | ![src50](data/output/sdv_rc50.png ) |
| 60          |  83.37    | ![src60](data/output/sdv_rc60.png ) |
| 70          |  80.60    | ![src70](data/output/sdv_rc70.png ) |
| 80          |  77.83    | ![src80](data/output/sdv_rc80.png ) |
| 90          |  75.06    | ![src90](data/output/sdv_rc90.png ) |
| 100         |  72.29%    | ![src100](data/output/sdv_rc100.png ) |


### Comparing the two different approaches
 1.Reconstruction for PCA is better at a lower value of number of prncipal components
 
 2.The compression ratio higher in PCA for the same value of component in PCA and K value in SVD
 
   
