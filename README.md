# Develop and test microservices with Kubernetes and Helm

### Continuously deliver a microservices app on Kubernetes using quality gates and Helm release coordination
Get started with this sample, which is an online store that consists of three microservices: a Catalog API, an Orders API, and a UI that calls both of the APIs. The sample includes a DevOps toolchain that is preconfigured for continuous delivery, hosted Git source control, functional testing, issue tracking, online editing, and messaging.

This DevOps process uses a combination of continuous integration (CI) and continuous deployment (CD) pipelines, to orchestrate microservices individually developed into coordinated releases that get promoted through distinct environments. A coordinated release is defined as a Helm umbrella chart, aggregating good versions of individual component Helm charts managed by the CI/CD process.

![Icon](./pics/umbrella-toolchain.png)

### To get started, click this button:
[![Create toolchain](https://cloud.ibm.com/devops/graphics/create_toolchain_button.png)](https://cloud.ibm.com/devops/setup/deploy?repository=https%3A%2F%2Fgithub.com%2Fopen-toolchain%2Fmicroservices-helm-toolchain&env_id=ibm:yp:us-south)
---
### Learn more 

* [Step by step tutorial](https://www.ibm.com/cloud/architecture/tutorials/use-develop-test-microservices-with-kubernetes-and-helm-toolchain)
* [Getting started](https://cloud.ibm.com/devops)
* [Documentation](https://cloud.ibm.com/docs/services/ContinuousDelivery?topic=ContinuousDelivery-getting-started&pos=2)
* [Toolchains on the IBM Cloud Garage Method site](https://www.ibm.com/garage/method/develop)
