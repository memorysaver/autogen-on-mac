# Autogen on Mac with local LLM

A concise guide for configuring Autogen and Autogen-Studio on Mac, with a focus on the local LLM.

## Install Ollama

```
To run a local LLM, install Ollama. If you succeed, you will see a little llama icon on your menu bar.

[Ollama for mac](https://ollama.ai/)

```

## Install AutgenStudio and litellm

you can simply run `poetry install` to install all requred packages or do it on your own.

```
pip install autogenstudio

## this pip is to proxy the local LLM and expose as OpenAI standard.
pip install 'litellm[proxy]'

```

## Configure your LLM backend.

this step is to launch local llm with ollama and expose OpenAI standard API.

```
ollama run mistral

# this will expose API at http://0.0.0.0:8000
litellm --model ollama/mistral

# this is to configure fallback backend.
export OPENAI_API_KEY={YOUR_OPENAI_KEY}
```

## Launch autogen-studio

```
autogenstudio ui --port 8081
```
