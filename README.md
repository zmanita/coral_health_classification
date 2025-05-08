based on Universal Remote Observation of Coral Health
by Lisa Pink, Matthew Johnson, Mohamad Ali Kalassina, Patrick Geitner, Thomas Durkin
https://github.com/patgeitner/nasa-coral-health-observation.git

Data Collection
1). After downloading the benthic map data from a given region, the SetupAllenCoralData is used to process the data into a format that can easily be merged with the satellite data. The notebook returns a subset from the given Allen Coral Data with an even number of Coral/Algae and non-Coral/Algae observations.

2). With the coral data sampled and processed into a pickle files, we can then add the necessary satellite data using Google Earth Engine. The CollectSatelliteData notebook reads in the resulting pickle file and adds surface reflectance features from the Modis-Aqua satellite and surface reflectance values and spectral indices from the Landsat-8 satellite. The resulting dataset is a spatially and temporally fused combination of the satellite features and coral labels that can be used to train our modeling approaches.

Feature Engineering
1). The Sea Surface Temperature Feature Extraction notebook explores extracting features related to sea surface temperatures, a factor known to contribute to coral bleaching

2). The chlorophyllA_feature_analysis notebook explores the correlation between various features relating to cholorphyll A concentration and particulate organic carbon with the percentage of bleaching that a coral colony has experienced.

Modeling 
1). The CoralPresenceModeling notebook walks through the training and evaluation of a gradient-boosted tree-based (XGBoost) model for predicting coral/algae presence at a given location using satellite data.

2). The AlgaeIdentification notebook walks through our temporal, voting-based method to determine if a given point contains coral or algae.
