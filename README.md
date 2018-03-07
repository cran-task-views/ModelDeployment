CRAN Task View: Model Deployment in R
-------------------------------------

|                 |                                                     
|-----------------|---------------------------------------------------  
| **Maintainer:** | Yuan Tang                                           
| **Contact:**    | terrytangyuan at gmail.com                          
| **Version:**    | 2018-03-07                                          
| **URL:**        | <https://CRAN.R-project.org/view=ModelDeployment>   

This CRAN task view contains a list of packages, grouped by topic, that
provides functionalities to streamline the process of deploying models
to scoring or inferencing on new data on various environments, such as
mobile devices, edge devices, cloud, GPUs, etc.

Deploying models is often challenging due to the following reasons:

-   It involves deploying models on heterogenous environments, e.g. edge
    devices, mobile devices, GPUs, etc.
-   It is hard to compress the model to very small size that could fit
    on devices with limited storage while avoiding high overhead to
    decompress it before model inference.
-   It is hard to make sure the trained model can process new data
    records within limited memory.
-   Not all environments have good network connectivity so sometimes
    cloud solutions may not satisfy the requirements.

Unless otherwise mentioned, all packages presented with hyperlinks are
available from CRAN, the Comprehensive R Archive Network.

Many of the areas discussed in this Task View are undergoing rapid
change in industries and academia. Please send suggestions for additions
and extensions for this task view to the [task view
maintainer](mailto:terrytangyuan@gmail.com).

**Mobile/Edge Devices** This section includes packages that provides
functionalities to export the trained model to an artifact that could
fit in small devices such as mobile devices (e.g. Android, iOS) and edge
devices (Rasberri Pi). These packages are built based on different model
format. Predictive Model Markup Language (PMML) is an XML-based language
which provides a way for applications to define statistical and data
mining models and to share models between PMML compliant applications.
The following packages are based on PMML:

-   The [pmml](https://cran.r-project.org/package=pmml) package provides the main
    interface to PMML.
-   The
    [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations)
    package allows for data to be transformed before using it to
    construct models. Builds structures to allow functions in the PMML
    package to output transformation details in addition to the model in
    the resulting PMML file.
-   The [rattle](https://cran.r-project.org/package=rattle) package allows to load
    data from a CSV file (or via ODBC), transform and explore the data,
    build and evaluate models, and export models as PMML or as scores.

### CRAN packages:

-   [pmml](https://cran.r-project.org/package=pmml)
-   [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations)
-   [rattle](https://cran.r-project.org/package=rattle)

### Related links:

-   [GitHub repository for this Task
    View](https://github.com/terrytangyuan/ctv-model-deployment)
