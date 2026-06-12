# Running AI Locally: Tools, Assistants, and Coding on Your Own Hardware
This is the repository for the LinkedIn Learning course `Running AI Locally: Tools, Assistants, and Coding on Your Own Hardware`. The full course is available from [LinkedIn Learning][lil-course-url].

![lil-thumbnail-url]

## Course Description

_See the readme file in the main branch for updated instructions and information._

Explore the process of running AI models locally to establish control over your solutions with regards to privacy, latency, and cost. Learn how to set up a local AI stack, including understanding models, runtimes, and integration with your hardware. Discover ways to deploy feature-rich AI assistants and tools that enhance your coding workflows. Evaluate practical scenarios for using offline language models on mobile devices. This course is designed with developers, software engineers, and IT professionals in mind, offering intermediate-level insights suitable for technical professionals eager to experiment with AI-powered tools. By applying the knowledge gained, you can effectively incorporate AI into personal or professional workflows without cloud dependencies. This hands-on approach to local AI enhances understanding and skill in deploying systems tailored to specific needs.

## Instructions
This repository has resources and configuration files from the course.

### Open WebUI Assistant

Before starting Open WebUI, install Ollama from the official site only after you have approval to do so and have checked the installer's safety at the time of download. Only download software if you understand and accept the risks.

If approved and verified as safe at the time of download, you can install Ollama with:

```sh
curl -fsSL https://ollama.com/install.sh | sh
```

If approved, you can also launch the local assistants with:

### Warning: launching these apps may change your default local configurations.

```sh
ollama launch claude
ollama launch codex-app
```

### Suggested Open-Weight Models by Hardware

Use the table below as a starting point when choosing a model for your device.

| Hardware tier | Suitable device | Suggested model | Ollama command | Notes |
| --- | --- | --- | --- | --- |
| Mobile and low-resource computers | Phones, tablets, older laptops, and small mini PCs | `gemma4:e4b` | `ollama pull gemma4:e4b` | Best fit when memory and compute are limited. |
| 16 GB+ fast memory | Macs with 16 GB+ unified memory or GPUs with about 16 GB VRAM | `gemma4:12b` | `ollama pull gemma4:12b` | Good balance of speed and quality on mainstream local hardware. |
| 24 GB+ fast memory | High-end consumer GPUs or larger-memory Macs | `gemma4:26b` | `ollama pull gemma4:26b` | Better quality, but needs more memory and bandwidth. |
| 32 GB+ fast memory | Workstations with large VRAM pools or high-memory unified-memory systems | `qwen3.6:35b` | `ollama pull qwen3.6:35b` | Use when you can afford slower responses for a larger model. |
| Medium-resource hardware | Strong laptops and desktops with comfortable local headroom | Mistral 3.5 | Check the current Ollama library name before pulling. | Dense model that requires more resources. |
| High-resource hardware | Powerful workstations and servers with substantial VRAM or RAM | GLM 5.1, DeepSeek V4, Nemotron 3 Super, MiniMax 2.7, MiniMax 3, Kimi K2.7 | Check the current Ollama library names before pulling. | Generally best suited for large-memory systems. Some quantizations may work on one or two DGX Spark systems or high-end Macs with lots of fast memory. |

Always verify the exact model name and tag in the Ollama library before running a pull command, since availability and naming may change.

For `llama-server` (`llama.cpp`), Unsloth workflows, and deployment guides, see [Unsloth model tutorials](https://unsloth.ai/docs/models/tutorials) and [NVIDIA Spark build guides](https://build.nvidia.com/spark).

### Create Ollama Models from This Repository

This repository includes Ollama Modelfiles in [modelfiles/](/Users/ronysheer/linked_in_courses/running-ai-locally-tools-assistants-and-coding-on-your-own-hardware-27483046/modelfiles) that you can build with `ollama create`.

From the repository root, run:

```sh
ollama create gemma4-agent -f modelfiles/Gemma4-Agent.Modelfile
ollama create gemma4-26b-agent -f modelfiles/Gemma4-26b-Agent.Modelfile
```

These commands create local Ollama models using the settings defined in the included Modelfiles.

To start the Open WebUI assistant from this repository:

```sh
cd open_webui
docker compose up
```

This starts the services defined in [open_webui/docker-compose.yml](~/linked_in_courses/running-ai-locally-tools-assistants-and-coding-on-your-own-hardware-27483046/open_webui/docker-compose.yml). Use `Ctrl+C` to stop them, or run `docker compose up -d` if you want to keep them running in the background.

## Installing
1. To use these exercise files, you must have the following installed:
	- Docker Desktop or another Docker engine with Compose support
	- Ollama
2. Clone this repository into your local machine using the terminal (Mac), CMD (Windows), or a GUI tool like SourceTree.
3. Start the Open WebUI assistant by following the steps in the section above.

## Instructor

Ronnie Sheer

Check out my other courses on [LinkedIn Learning]([https://www.linkedin.com/learning/instructors/](https://www.linkedin.com/learning/instructors/ronnie-sheer?u=104).


[0]: # (Replace these placeholder URLs with actual course URLs)

[lil-course-url]: https://www.linkedin.com/learning/running-ai-locally-tools-assistants-and-coding-on-your-own-hardware
[lil-thumbnail-url]: https://media.licdn.com/dms/image/v2/D560DAQFWSzwyUz8kDw/learning-public-crop_675_1200/B56Z5Mdge2HsAY-/0/1779399264547?e=2147483647&v=beta&t=TuOgA01M9-1dZqaOe3TYjVV2Fdw-Ni_4f2h5ZOlMU4Y

