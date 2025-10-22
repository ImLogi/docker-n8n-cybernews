# Cyber News
![Docker](https://img.shields.io/badge/Docker-ready-blue?logo=docker)
![n8n](https://img.shields.io/badge/n8n-automation-ef476f?logo=n8n&logoColor=white)
![Ollama](https://img.shields.io/badge/-Ollama-000000?style=flat&logo=ollama&logoColor=white)

# 🚧 Work in Progress

> This project is currently under active development.
> Features and documentation may change at any time.


## Objective
Build an automated AI agent that aggregates the latest cybersecurity news from selected websites, produces a shortened combined summary, deliver it via email and provides links to original sources.

>Note: Response time and output quality depend on the chosen AI model and host system's specifications.

## Tools
[n8n](https://n8n.io/) — a powerful workflow automation tool.
I chose n8n for its ability to be easily deployed and used locally.

[Docker](https://www.docker.com/) — incredible tool for building, sharing and running applications.

[Ollama](https://ollama.com/) — open-source software for running LLMs locally. Build-in integration with n8n.


## Features
**This project uses ONLY free and open-source tools, promoting privacy, independence and cost-free accessibility for enthusiast who value the open-source philosophy**
>Note: The intended use case for this project is individual or educational purposes. For any other type of usee, you may want to review the license terms and applicable policies.


This project provides a ready-to-use Docker Compose configuration for running n8n and Ollama locally. You can use my provided configuration (set to the Europe/Warsaw timezone, uses Nvidia GPU), modify it to match your own needs or create your own setup following the [n8n Docker installation guide](https://docs.n8n.io/hosting/installation/docker/) and [Ollama Docker installation guide](https://docs.ollama.com/docker).


## Prerequisites

[Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/)


## Installation


### 1. Ensure Docker and Docker Compose are installed

``` BASH
docker -v
docker compose version
```


### 2. Clone repo

``` BASH
git clone https://github.com/ImLogi/docker-n8n-cybernews.git
cd docker-n8n-cybernews
```


### 3. Run Docker Compose

``` BASH
docker compose up -d
```


### 4. Ensure containers was successfully deployed

``` BASH
docker ps -a
```

You should see containers with names: n8n, ollama.

### 4.1 (Optional) Check connetion

Ollama API is available at:

```
http://localhost:11434
```

>Note: If you go to Ollama API addres, the only thing you will see is *Ollama is running* 

n8n interface is available at:

```
http://localhost:5678
```


### 5. Chose your model

To download certain model to ollama use:

``` BASH
docker exec -it ollama ollama pull [model_name]
```

For full list check [Ollama Library](https://ollama.com/library)

Or you can use any of this:
 
| Model | Parameters | Size | [model_name] | Comment |
|:--|:--:|:--:|:--:|--:|
|Moondream 2|1.4B|829MB|`moondream`|smallest model, only for connection tests|
|Gemma 3|12B|8.1GB|`gemma3:12b`|small model, a little bit smarter|
|Llama 3.2 Vision|11B|7.9GB|`llama3.2-vision`| alternative to Gemma 3|
|Llama 4|109B|67GB|`llama4:scout`| solid model, yet demanding|
|DeepSeek-R1|671B|404GB|`deepseek-r1:671b`|good luck|

>Note: You should have at least 8 GB of RAM available to run the 7B models, 16 GB to run the 13B models, and 32 GB to run the 33B models.


### 6. ...
