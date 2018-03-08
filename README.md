## CRAN Task View: Model Deployment in R

|                 |                                                     
| --------------- | -------------------------------------------------   
| **Maintainer:** | Yuan Tang                                           
| **Contact:**    | terrytangyuan at gmail.com                          
| **Version:**    | 2018-03-07                                          
| **URL:**        | <https://CRAN.R-project.org/view=ModelDeployment>   

<div>

This CRAN task view contains a list of packages, grouped by topic, that
provides functionalities to streamline the process of deploying models
to scoring or inferencing on new data on various environments, such as
mobile devices, edge devices, cloud, GPUs, etc.

Deploying models is often challenging due to the following reasons:

  - It involves deploying models on heterogenous environments, e.g. edge
    devices, mobile devices, GPUs, etc.
  - It is hard to compress the model to very small size that could fit
    on devices with limited storage while avoiding high overhead to
    decompress it before model inference.
  - It is hard to make sure the trained model can process new data
    records within limited memory.
  - Not all environments have good network connectivity so sometimes
    cloud solutions may not satisfy the requirements.

Many of the areas discussed in this Task View are undergoing rapid
change in industries and academia. Please send suggestions for additions
and extensions for this task view to the [task view
maintainer](mailto:terrytangyuan@gmail.com).

**Mobile/Edge Devices**

This section includes packages that provides functionalities to export
the trained model to an artifact that could fit in small devices such as
mobile devices (e.g. Android, iOS) and edge devices (Rasberri Pi). These
packages are built based on different model format.

Predictive Model Markup Language (PMML) is an XML-based language which
provides a way for applications to define statistical and data mining
models and to share models between PMML compliant applications. The
following packages are based on PMML:

  - The [pmml](https://cran.r-project.org/package=pmml) package provides the main
    interface to PMML.
  - The
    [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations)
    package allows for data to be transformed before using it to
    construct models. Builds structures to allow functions in the PMML
    package to output transformation details in addition to the model in
    the resulting PMML file.
  - The [rattle](https://cran.r-project.org/package=rattle) package allows to load
    data from a CSV file (or via ODBC), transform and explore the data,
    build and evaluate models, and export models as PMML or as scores.

Plain Old Java Object (POJO) or a Model ObJect, Optimized (MOJO) are
intended to be easily embeddable in any Java environment. The only
compilation and runtime dependency for a generated model is a .jar file
produced as the build output of these packages. The
[h2o](https://cran.r-project.org/package=h2o) package provides easy-to-use interface
to build machine learning models that can then be exported as MOJO and
POJO format.

[TensorFlow](https://www.tensorflow.org/) 's ExportedModel or a soon
coming optimized version on small devices called TensorFlow Lite, which
uses many techniques for achieving low latency such as optimizing the
kernels for mobile apps, pre-fused activations, and quantized kernels
that allow smaller and faster (fixed-point math) models. It enables
on-device machine learning inference with low latency and small binary
size. The following packages can produce models in this format:

  - The [tfestimators](https://cran.r-project.org/package=tfestimators) package
    provides high-level API to machine learning models as well as highly
    customized neural network architectures.
  - The [keras](https://cran.r-project.org/package=keras) package high-level API to
    construct different types of neural networks.

Portable Format for Analytics (PFA) is a specification for event-based
processors that perform predictive or analytic calculations and is aimed
at helping smooth the transition from statistical model development to
large-scale and/or online production. The
[aurelius](https://cran.r-project.org/package=aurelius) package provides tools for
converting R objects and syntax into the PFA format.

Additionally, the [onnx](https://cran.r-project.org/package=onnx) package provides
the interface to [Open Neural Network Exchange (ONNX)](https://onnx.ai/)
which is a standard format for models built using different frameworks
(e.g. TensorFlow, MXNet, PyTorch, etc).

**Cloud/server-based Environments**

Many deployment environments are based on cloud/server. The following
packages provides functionalities to deploy models in those types of
environments:

  - The [yhatr](https://cran.r-project.org/package=yhatr) package allows to deploy,
    maintain, and invoke models via the [Yhat](https://www.yhat.com)
    REST API.
  - The [cloudml](https://github.com/rstudio/cloudml) package provides
    functionality to easily deploy models to [Google Cloud ML
    Engine](https://cloud.google.com/ml-engine/).
  - The [domino](https://cran.r-project.org/package=domino) package provides R
    interface to [Domino](https://www.dominodatalab.com/) CLI, a service
    that makes it easy to run your code on scalable hardware, with
    integrated version control and collaboration features designed for
    analytical workflows.
  - The [tidypredict](https://cran.r-project.org/package=tidypredict) package
    provides functionalities to run predictions inside database.
  - The [AzureML](https://cran.r-project.org/package=AzureML) package contains
    functions and datasets to support Azure Machine Learning. This
    allows you to interact with datasets, as well as publish and consume
    R functions as API services.
  - [DeployR Open](http://projects.revolutionanalytics.com/deployr/) is
    a server-based framework for integrating R into other applications
    via Web Services.
  - The [opencpu](https://cran.r-project.org/package=opencpu) package provides a
    server that exposes a simple but powerful HTTP API for RPC and data
    interchange with R. This provides a reliable and scalable foundation
    for statistical services or building R web applications.
  - Several general purpose server/client frameworks for R exist that
    could help deploy models in server based environments:
      - The [Rserve](https://cran.r-project.org/package=Rserve) and
        [RSclient](https://cran.r-project.org/package=RSclient) packages both
        provide server and client functionality for TCP/IP or local
        socket interfaces.
      - The [httpuv](https://cran.r-project.org/package=httpuv) package provides a
        low-level socket and protocol support for handling HTTP and
        WebSocket requests directly within R.
  - Several packages offer functionality for turning R code into a web
    API:
      - The [jug](https://cran.r-project.org/package=jug) package is a simple
        API-builder web framework, built around
        [httpuv](https://cran.r-project.org/package=httpuv).
      - The [FastRWeb](https://cran.r-project.org/package=FastRWeb) package provides
        some basic infrastructure for this. plumber allows you to create
        a REST API by decorating existing R source code.

</div>

### CRAN packages:

  - [aurelius](https://cran.r-project.org/package=aurelius)
  - [AzureML](https://cran.r-project.org/package=AzureML)
  - [domino](https://cran.r-project.org/package=domino)
  - [FastRWeb](https://cran.r-project.org/package=FastRWeb)
  - [h2o](https://cran.r-project.org/package=h2o)
  - [httpuv](https://cran.r-project.org/package=httpuv)
  - [jug](https://cran.r-project.org/package=jug)
  - [keras](https://cran.r-project.org/package=keras)
  - [onnx](https://cran.r-project.org/package=onnx)
  - [opencpu](https://cran.r-project.org/package=opencpu)
  - [pmml](https://cran.r-project.org/package=pmml)
  - [pmmlTransformations](https://cran.r-project.org/package=pmmlTransformations)
  - [rattle](https://cran.r-project.org/package=rattle)
  - [RSclient](https://cran.r-project.org/package=RSclient)
  - [Rserve](https://cran.r-project.org/package=Rserve)
  - [tfestimators](https://cran.r-project.org/package=tfestimators)
  - [tidypredict](https://cran.r-project.org/package=tidypredict)
  - [yhatr](https://cran.r-project.org/package=yhatr)

### Related links:

  - [GitHub repository for this Task
    View](https://github.com/terrytangyuan/ctv-model-deployment)
