# The Ultimate Engineer Toolbox <img src="https://www.shareicon.net/data/128x128/2017/04/11/883708_media_512x512.png" alt="YouTube" width="5%" height="5%"> :hammer::wrench:

A Collection of tools, hands-on walkthroughs with source code. <br/>
The Ultimate Swiss Army knife for DevOps, Developers and Platform Engineers

<br/>


## About this repository

This repo holds the source code and walkthroughs that accompany the YouTube tutorials by Marcel Dempers on DevOps, development and platform engineering. It is a fork of [marcel-dempers/docker-development-youtube-series](https://github.com/marcel-dempers/docker-development-youtube-series). Several links below still point to the upstream repo and its branches (for example `part1`, `part2` and `debugging-python`).

### Repository layout

| Area | Folders |
|---|---|
| Languages and sample apps | [`c#`](./c%23), [`golang`](./golang), [`nodejs`](./nodejs), [`python`](./python), [`springboot`](./springboot), [`deno`](./deno) |
| Kubernetes and GitOps | [`kubernetes`](./kubernetes), [`argo`](./argo), [`flux`](./flux) |
| CI/CD | [`jenkins`](./jenkins), [`drone-ci`](./drone-ci), [`github`](./github), [`.github`](./.github) |
| Observability | [`monitoring`](./monitoring), [`tracing`](./tracing) |
| Infrastructure and other tools | [`apache`](./apache), [`hashicorp`](./hashicorp), [`messaging`](./messaging), [`security`](./security), [`storage`](./storage) |

### Local development with Docker Compose

The root [`docker-compose.yaml`](./docker-compose.yaml) (version 3.4) defines services for local development and debugging. Each service builds from its language folder, mounts the source code as a volume, and is tagged `aimvector/<name>:1.0.0`.

| Service | Build context | Build target | Ports (host:container) |
|---|---|---|---|
| `csharp` | `./c#` | `debug` | 5000:5000 |
| `golang` | `./golang` | `prod` | 5001:5000 (app), 2345:2345 (debugger) |
| `python` | `./python` | `debug` | 5003:5000 (app), 5678:5678 (debugger) |
| `nodejs` | `./nodejs` | `debug` | 5002:5000 (app), 9229:9229 (debugger) |
| `spring-java` | `./springboot/java/` | `debug` | 9999:8080 |

Notes:
- The `golang` service also mounts the `configs` and `secrets` folders. It runs with `seccomp:unconfined`, which the Delve debugger needs.
- The `spring-java` service starts with a shell entrypoint and an interactive TTY.

```
docker-compose up --build <service>
```


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
