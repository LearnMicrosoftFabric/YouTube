# Data Validation with Microsoft Fabric using Great Expectations 

## Motivation 
You should validate your data. Always. You owe it to your dashboard users/ analysis users. And it gives you peace of mind. 

## Great Expectations
[Great Expectations](https://docs.greatexpectations.io/) is a comprehensive data testing and validation framework (Python). It's pretty much the industry standard, so it makes sense to learn how to apply it in the Fabric context. 

## Approach
The solution provided in the two notebooks has been developed with a Medallion architecture in mind; it provides the mechanism to validate your data between Bronze and Silver lakehouse tables. 

There are two notebooks in this folder:
1) The first notebook ('Part 1') is for setting up your Great Expectations configuration (known as the Data Context), you just need to work through it once, and this will create your Context which is then stored in your Lakehouse Files.
2) The second notebook ('Part 2') it build to be embedded within a Fabric data pipeline; i.e. it is meant to perform runtime validation of Bronze data, based on the configuration we worked through in Part 1, and if all validation steps are passed, it loads the validated data into a Silver table.   

## Limitations/ Possible extensions in the future 
These notebooks were created around August 2023, before there was any formal integration between Great Expectations and Fabric. I expect in the future it will be easier to integrate the two. 
Currently, the configuration is only setup to validate one dataset, this was done to make the training tutorial as easy to follow as possible. 
In the future, thsi work could be extended by: 
- adding more 'coverage' i.e. adding more Expectations based on domain knowledge
- adding more datasets to be validated
- adding better handling of errors (perhaps quarantining data for review)
- differentiating between hard fails (errors) and warnings (warnings)
