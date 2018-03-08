CRAN Task View: Model Deployment with R
---------------------------------------

|                 |                                                     
|-----------------|---------------------------------------------------  
| **Maintainer:** | Yuan Tang                                           
| **Contact:**    | terrytangyuan at gmail.com                          
| **Version:**    | 2018-03-08                                          
| **URL:**        | <https://CRAN.R-project.org/view=ModelDeployment>   

This CRAN task view contains a list of packages, grouped by topic, that provides functionalities to streamline the process of deploying models to various environments, such as mobile devices, edge devices, cloud, and GPUs, for scoring or inferencing on new data.

Model deployment is often challenging due to various reasons. Some example challenges are:

-   It involves deploying models on heterogenous environments, e.g. edge devices, mobile devices, GPUs, etc.
-   It is hard to compress the model to very small size that could fit on devices with limited storage while keeping the same precision and small overhead to load the model before inference.
-   Deployed models sometimes need to process new data records within limited memory on small devices.
-   Many deployment environments have bad network connectivity so sometimes cloud solutions may not meet the requirements.
-   There's interest in stronger user data privacy paradigms where user data does not need to leave the mobile device.
-   There's growing demand to perform on-device model-based data filtering before collecting the data.

Many of the areas discussed in this task view are undergoing rapid changes in industries and academia. Please send suggestions for this task view to the [task view maintainer](mailto:terrytangyuan@gmail.com).

**Deployment through Different Types of Artifacts**

This section includes packages that provides functionalities to export the trained model to an artifact that could fit in small devices such as mobile devices (e.g. Android, iOS) and edge devices (Rasberri Pi). These packages are built based on different model format.

-   Predictive Model Markup Language (PMML) is an XML-based language which provides a way for applications to define statistical and data mining models and to share models between PMML compliant applications. The following packages are based on PMML:
    -   The [pmml](https://cran.r-project.org/package=pmml) package provides the main interface to PMML.
    -   The [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations) package allows for data to be transformed before using it to construct models. Builds structures to allow functions in the PMML package to output transformation details in addition to the model in the resulting PMML file.
    -   The [rattle](https://cran.r-project.org/package=rattle) package allows to load data from a CSV file (or via ODBC), transform and explore the data, build and evaluate models, and export models as PMML or as scores.
-   Plain Old Java Object (POJO) or a Model ObJect, Optimized (MOJO) are intended to be easily embeddable in any Java environment. The only compilation and runtime dependency for a generated model is a .jar file produced as the build output of these packages. The [h2o](https://cran.r-project.org/package=h2o) package provides easy-to-use interface to build machine learning models that can then be exported as MOJO and POJO format.
-   Portable Format for Analytics (PFA) is a specification for event-based processors that perform predictive or analytic calculations and is aimed at helping smooth the transition from statistical model development to large-scale and/or online production. The [aurelius](https://cran.r-project.org/package=aurelius) package provides tools for converting R objects and syntax into the PFA format.
-   [TensorFlow](https://www.tensorflow.org/) ExportedModel as well as its optimized version [TensorFlow Lite](https://www.tensorflow.org/mobile/tflite/), which uses many techniques for achieving low latency such as optimizing the kernels for mobile apps, pre-fused activations, and quantized kernels that allow smaller and faster (fixed-point math) models. It enables on-device machine learning inference with low latency and small binary size. The following packages can produce models in this format:
    -   The [tensorflow](https://cran.r-project.org/package=tensorflow) package provides full access to TensorFlow API for numerical computation using data flow graphs.
    -   The [tfestimators](https://cran.r-project.org/package=tfestimators) package provides high-level API to machine learning models as well as highly customized neural network architectures.
    -   The [keras](https://cran.r-project.org/package=keras) package high-level API to construct different types of neural networks.
-   The [onnx](https://cran.r-project.org/package=onnx) package provides the interface to [Open Neural Network Exchange (ONNX)](https://onnx.ai/) which is a standard format for models built using different frameworks (e.g. TensorFlow, MXNet, PyTorch, etc).

**Deployment through Cloud/Server**

Many deployment environments are based on cloud/server. The following packages provides functionalities to deploy models in those types of environments:

-   The [yhatr](https://cran.r-project.org/package=yhatr) package allows to deploy, maintain, and invoke models via the [Yhat](https://www.yhat.com) REST API.
-   The [cloudml](https://github.com/rstudio/cloudml) package provides functionality to easily deploy models to [Google Cloud ML Engine](https://cloud.google.com/ml-engine/).
-   The [tfdeploy](https://github.com/rstudio/tfdeploy) package provides functions to run a local test server that supports the same REST API as CloudML and [RStudio Connect](https://www.rstudio.com/products/connect/).
-   The [domino](https://cran.r-project.org/package=domino) package provides R interface to [Domino](https://www.dominodatalab.com/) CLI, a service that makes it easy to run your code on scalable hardware, with integrated version control and collaboration features designed for analytical workflows.
-   The [tidypredict](https://cran.r-project.org/package=tidypredict/index.html) package provides functionalities to run predictions inside database. It's based on [dplyr](../packages/dplyr/index.html) and [dbplyr](../packages/dbplyr) that could translate data manipulations written in R to database queries that can be used later to execute the data transformations and aggregations inside various types of databases.
-   The [sparklyr](https://cran.r-project.org/package=sparklyr/index.html) package provides bindings to [Apache Spark](https://spark.apache.org/) 's distributed machine learning library and allows to deploy the trained models to clusters. Additionally, the [rsparkling](../packages/rsparkling/index.html) package uses [sparklyr](../packages/sparklyr/index.html) for Spark job deployment while using [h2o](../packages/h2o) package for regular model building.
-   The [AzureML](https://cran.r-project.org/package=AzureML) package contains functions and datasets to support [Azure Machine Learning](https://azure.microsoft.com/en-us/overview/machine-learning/). This allows you to interact with datasets, as well as publish and consume R functions as API services.
-   [DeployR Open](http://projects.revolutionanalytics.com/deployr/) is a server-based framework for integrating R into other applications via Web Services.
-   The [opencpu](https://cran.r-project.org/package=opencpu) package provides a server that exposes a simple but powerful HTTP API for RPC and data interchange with R. This provides a reliable and scalable foundation for statistical services or building R web applications.
-   Several general purpose server/client frameworks for R exist that could help deploy models in server based environments:
    -   The [Rserve](https://cran.r-project.org/package=Rserve/index.html) and [RSclient](../packages/RSclient) packages both provide server and client functionality for TCP/IP or local socket interfaces.
    -   The [httpuv](https://cran.r-project.org/package=httpuv) package provides a low-level socket and protocol support for handling HTTP and WebSocket requests directly within R.
-   Several packages offer functionality for turning R code into a web API:
    -   The [jug](https://cran.r-project.org/package=jug/index.html) package is a simple API-builder web framework, built around [httpuv](../packages/httpuv).
    -   The [FastRWeb](https://cran.r-project.org/package=FastRWeb) package provides some basic infrastructure for this. plumber allows you to create a REST API by decorating existing R source code.

### CRAN packages:

-   [aurelius](https://cran.r-project.org/package=aurelius)
-   [AzureML](https://cran.r-project.org/package=AzureML)
-   [dbplyr](https://cran.r-project.org/package=dbplyr)
-   [domino](https://cran.r-project.org/package=domino)
-   [dplyr](https://cran.r-project.org/package=dplyr)
-   [FastRWeb](https://cran.r-project.org/package=FastRWeb)
-   [h2o](https://cran.r-project.org/package=h2o)
-   [httpuv](https://cran.r-project.org/package=httpuv)
-   [jug](https://cran.r-project.org/package=jug)
-   [keras](https://cran.r-project.org/package=keras)
-   [onnx](https://cran.r-project.org/package=onnx)
-   [opencpu](https://cran.r-project.org/package=opencpu)
-   [pmml](https://cran.r-project.org/package=pmml)
-   [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations)
-   [rattle](https://cran.r-project.org/package=rattle)
-   [RSclient](https://cran.r-project.org/package=RSclient)
-   [Rserve](https://cran.r-project.org/package=Rserve)
-   [rsparkling](https://cran.r-project.org/package=rsparkling)
-   [sparklyr](https://cran.r-project.org/package=sparklyr)
-   [tensorflow](https://cran.r-project.org/package=tensorflow)
-   [tfestimators](https://cran.r-project.org/package=tfestimators)
-   [tidypredict](https://cran.r-project.org/package=tidypredict)
-   [yhatr](https://cran.r-project.org/package=yhatr)

### Related links:

-   [GitHub repository for this Task View](https://github.com/terrytangyuan/ctv-model-deployment)
