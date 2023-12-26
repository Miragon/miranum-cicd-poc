# miranum-cicd-poc

## Overview
This projects is a POC that demonstrates the use of CI/CD pipelines and dependency management for an enhanced 
implementation process in process automation projects. The Spring Boot Service and the process artifacts were
taken from the [miranum-stack-showcase](https://github.com/Miragon/miranum-stack-showcase/tree/main) and then modified 
for this POC.

**This repository consists of:** 
- Process artifacts
- Spring boot service 
- GitHub workflows


## Process artifacts
The process artifacts are located in the [artifacts](artifacts) directory and were generated by using the miranum-ide 
plugin in VS-Code. To access the correct deployment-service the target environments in the [miranum.json](artifacts/miranum.json) 
file were modified accordingly.

The artifacts in this poc are also packaged in an NPM package. More information about that can be found in the respective 
[README.md](artifacts/README.md) file. 


## Springboot service
The Spring Boot service is taken from the miranum-stack-showcase and represents a service task in the process.

To use the artifacts in the Spring Boot Service the resource root of the service was modified in the 
[pom.xml](order-example/order-example-camunda7/pom.xml) file to include the artifacts directory.


## Pipelines
There are three main [workflows](.github/workflows) that are implemented in this project. 

### [Build](.github/workflows/build.yaml)
In the build workflow the project is built and every unit test is executed to ensure code quality. On test failure the build job
is going to fail. The linting job checks every .bpmn and .dmn file against the specified linting rules 
([bpmn](.bpmnlintrc), [dmn](.dmnlintrc)). 

Note that the linting job will not fail if any errors or warnings are detected 
during the check-up. 

### [Publish artifacts](.github/workflows/publish_artifacts.yaml)
In this workflow a new version of the NPM package can be published. Make sure to update the version in the 
[package.json](artifacts/package.json) file accordingly.

### [Deploy artifacts](.github/workflows/deploy_artifacts.yaml)
This workflow allows to deploy a process to the target specified in the [miranum.json](artifacts/miranum.json) file. 
Currently, the deployment will use the `test` target. 

To execute the deployment the process-ide-cli image is used. To further customize the deployment command please see the
[documentation](https://miranum.com/docs/components/miranum-ide/commands/deployment_api).


## License
This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Maintainer
Amin Yacine <amin.yacine@miragon.io>
