# The Ultimate Engineer Toolbox <img src="https://www.shareicon.net/data/128x128/2017/04/11/883708_media_512x512.png" alt="YouTube" width="5%" height="5%"> :hammer::wrench:

A Collection of tools, hands-on walkthroughs with source code. <br/>
The Ultimate Swiss Army knife for DevOps, Developers and Platform Engineers

## About this repository

This repository holds the source code, Dockerfiles and Kubernetes manifests that accompany a DevOps YouTube series by Marcel Dempers.
Each playlist or video in the tables below links to the folder (or branch) with the matching code,
so you can follow along and run the examples yourself.

This repo is a fork of [marcel-dempers/docker-development-youtube-series](https://github.com/marcel-dempers/docker-development-youtube-series).
Links to branches such as `part1`, `part2` and `part3` point to the original repository.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) with Docker Compose, for the Docker examples
- `kubectl` and a Kubernetes cluster (for example [kind](https://kind.sigs.k8s.io/)), for the Kubernetes examples

### Repository layout

| Folder | Contents |
|---|---|
| `c#/`, `golang/`, `python/`, `nodejs/`, `deno/`, `springboot/` | Sample apps and Dockerfiles for the Docker development basics |
| `kubernetes/` | Kubernetes guides: deployments, services, ingress, RBAC, Helm, Kustomize, autoscaling, cloud, service mesh and more |
| `monitoring/`, `tracing/` | Prometheus, logging and tracing examples |
| `argo/`, `flux/`, `drone-ci/`, `jenkins/`, `github/` | CI/CD and GitOps tools |
| `messaging/`, `storage/`, `apache/` | Kafka, RabbitMQ and Redis |
| `hashicorp/` | HashiCorp Vault |
| `security/` | Let's Encrypt |

### Running the sample apps

The root `docker-compose.yaml` defines a development container for the language examples.
From the repository root:

```
docker-compose build <service>
docker-compose up <service>
```

| Service | Host port(s) | Notes |
|---|---|---|
| `csharp` | 5000 | |
| `golang` | 5001, 2345 | 2345 is the Delve debug port |
| `nodejs` | 5002, 9229 | 9229 is the Node.js debug port |
| `python` | 5003, 5678 | 5678 is the debug port |
| `spring-java` | 9999 | |

See the comments in `docker-compose.yaml` for the equivalent `docker run` commands.

<br/>


| Steps  | Playlist :tv: | Source :octocat: | 
|---|---|---|
| Learn Kubernetes :snowflake:  | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVvUEdqaBeMK2awVThNujwMd" title="Kubernetes"><img src="https://i.ytimg.com/vi/8h4FoWK7tIA/hqdefault.jpg" width="50%" alt="Kubernetes Guide" /></a>  | [source](./kubernetes/readme.md)   | 
| Learn about CI/CD tools :whale: | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVsSsrnZimHEf7NJ1MlRhQUj" title="CI/CD"><img src="https://i.ytimg.com/vi/myCcJJ_Fk10/hqdefault.jpg" width="50%" alt="CI/CD Guide" /></a>  |   |   |   |
| Deploy Kubernetes to the cloud :partly_sunny: | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVsUhzNBkn-rPzXtPNpJu1-k" title="Cloud K8s"><img src="https://i.ytimg.com/vi/3jA9EfkSAUU/hqdefault.jpg" width="50%" alt="Cloud Guide" /></a>  | [source](./kubernetes/cloud/readme.md)  | 
| Monitoring Kubernetes :mag: | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVuEXCrRkPFWLXRKWNLOVUHn" title="Cloud K8s"><img src="https://i.ytimg.com/vi/5o37CGlNLr8/hqdefault.jpg" width="50%" alt="Cloud Guide" /></a>   | [source](./monitoring/prometheus/kubernetes/readme.md)  | 
| Guide to Logging :page_with_curl: | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVvfDxFW50Mdezk0xum-tyHT" title="Cloud K8s"><img src="https://i.ytimg.com/vi/MMVdkzeQ848/hqdefault.jpg" width="50%" alt="Cloud Guide" /></a>   | [source](./monitoring/logging/readme.md)  |  
| Guide to ServiceMesh :globe_with_meridians: | <a href="https://www.youtube.com/playlist?list=PLHq1uqvAteVsmxHpGsMjTOROn3i99lzTA" title="Cloud K8s"><img src="https://i.ytimg.com/vi/rVNPnHeGYBE/hqdefault.jpg" width="50%" alt="Cloud Guide" /></a>   | [source](./kubernetes/servicemesh/readme.md)  |


## Docker Development Basics


| Step :heavy_check_mark:  | Video :movie_camera: | Source Code :octocat: |
|---|---|---|
| Working with `Dockerfiles` <br/>(.NET, Golang, Python, NodeJS) | <a href="https://youtu.be/wyjNpxLRmLg" title="Docker 1"><img src="https://i.ytimg.com/vi/wyjNpxLRmLg/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/part1)  |
| Working with code <br/>(.NET, Golang, Python, NodeJS) | <a href="https://youtu.be/EdmKENqnQUw" title="Docker 1"><img src="https://i.ytimg.com/vi/EdmKENqnQUw/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/part2)  |
| Docker Multistage explained  | <a href="https://youtu.be/2lQ7WrwpZfI" title="Docker 1"><img src="https://i.ytimg.com/vi/2lQ7WrwpZfI/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/part3)  |
| Debugging Go in Docker  | <a href="https://youtu.be/kToyI16IFxs" title="Docker 1"><img src="https://i.ytimg.com/vi/kToyI16IFxs/hqdefault.jpg" width="50%" alt="Docker 1" /></a> | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/master/golang)  |
| Debugging .NET in Docker  | <a href="https://youtu.be/ds2bud0ZYTY" title="Docker 1"><img src="https://i.ytimg.com/vi/ds2bud0ZYTY/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/part5)  |
| Debugging Python in Docker  | <a href="https://youtu.be/b78Tg-YmJZI" title="Docker 1"><img src="https://i.ytimg.com/vi/b78Tg-YmJZI/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/debugging-python)  |
| Debugging NodeJS in Docker  | <a href="https://youtu.be/ktvgr9VZ4dc" title="Docker 1"><img src="https://i.ytimg.com/vi/ktvgr9VZ4dc/hqdefault.jpg" width="50%" alt="Docker 1" /></a>  | [source](https://github.com/marcel-dempers/docker-development-youtube-series/tree/master/nodejs)  |

## Engineering Toolbox :hammer::wrench:


Checkout the toolbox [website](https://marceldempers.dev/toolbox)

<a href="https://marceldempers.dev/toolbox" title="toolbox 1"><img src="./toolbox.png" alt="toolbox 1" /></a>
