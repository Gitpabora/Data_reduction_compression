# CCE AIML - learning data compression for Machine learning
by 
### Shriti Singh
### Parinita Bora
# The algorithms experimented with with high resolution image data  as a part of preprocessing of data  :SVD, PCA, K-mean 

an example image 
<img align="right" src="https://github.com/Gitpabora/Data_reduction_compression/tree/main/data/sample_image.jpg" width="400">

A brief note about the methods
    |------------------------------------------------------------------------------------------------------------------------------------------|
    | Method                          | Inventor(s)                                                        | Purpose                           |
    |-------------------------------- | ------------------------------------------------------------------ |---------------------------------- | 
    |Singular Value Decomposition(SVD)| Independently Eugenio Beltrami, Camille Jordon over 100 yrs back   |To predict a set of optimal factors|
    |---------------------------------|--------------------------------------------------------------------|-----------------------------------|
    |Principal comonent Analysis(PCA) | Karl Pearson in 1901, later in 1930, developped by Harold Hotelling| dimnetionality reduction          |
    |---------------------------------|--------------------------------------------------------------------|-----------------------------------|
    |K-Means clustering               | First used by James MacQueen in 1967 ,used by Steinhaus in 1956    |In pulse code modulation(Steinhaus)|                              | 
    |------------------------------------------------------------------------------------------------------------------------------------------|





The detailed implementation  notepads 

https://drive.google.com/file/d/1_pBJL6v9sRRetdD0tLqvmihOVvtvivf8/view?usp=share_link
https://colab.research.google.com/drive/1eG843MHVTwohPAqRmsQa8JToxPNJZR1M?usp=share_link


##Experiment Results PCA







PCA compr
    | components  |  c ratio     |Explained variance                        | Reconstructed Image           |    Percentage Reduction
    |------------ | ------------- | -----------------------------------------|-------------------------------|------------------------|
    | 10          |  99.076202    |![](Data_reduction_compression/sample_data/output/Explained_variance10.png)
    | 20          |  98.152403    | Explained_variance20.png
    | 30          |  97.228605    | Explained_variance30.png
    | 40          |  96.304806    | Explained_variance40.png
    | 50          |  95.381008    | Explained_variance50.png
    | 60          |  94.457209    | Explained_variance10.png
    | 70          |  93.533411    | Explained_variance10.png
    | 80          |  92.609612    | Explained_variance10.png
    | 90          |  91.685814    | Explained_variance10.png
    | 100         |  90.762015    | Explained_variance10.png
