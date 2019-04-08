# Spring Boot Helm starter

This project provides a simple way to generate Kubernetes descriptors
using Helm, in order to deploy a Spring Boot app.
Using a single command, you create YAML files for your app: you just need
to customize these descriptors to set your container image, and you're done.

<img src="https://i.imgur.com/gZN0r7r.gif"/>

The generated descriptors support these features:
 - app deployment with healthchecks & replication
 - [Spring Cloud Kubernetes](https://spring.io/projects/spring-cloud-kubernetes) support
   (`ConfigMap`, `Secret`, service discovery, client-side load balancing)
 - default `ConfigMap` configuration
 - Prometheus support

**Using this Helm starter you don't need to write YAML files anymore!**

## How to use it?

Install this repository in your local Helm starter repository:
```bash
$ git clone https://github.com/alexandreroman/spring-boot-helm-starter.git $HOME/.helm/starters/spring-boot
```

Create an Helm chart for your app:
```bash
$ helm create --starter=spring-boot myapp
Creating myapp
```

Edit generated file `myapp/values.yml` and set your Docker image:
```yaml
image:
  repository: myrepo/myapp
```

As you can see, you can also set some properties in this file,
such as `ConfigMap` entries.

You are now ready to deploy your app using Helm:
```bash
$ helm install --namespace myns myapp
```

## Contribute

Contributions are always welcome!

Feel free to open issues & send PR.

## License

Copyright &copy; 2019 [Pivotal Software, Inc](https://pivotal.io).

This project is licensed under the [Apache Software License version 2.0](https://www.apache.org/licenses/LICENSE-2.0).
