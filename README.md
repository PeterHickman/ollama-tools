# ollama-tools
Some tools to make playing with ollama easier from the command line

## ollama-models

```bash
$ ollama-models
Name                     Description
------------------------ ---------------------------------------------------------------...
alfred                   A robust conversational model designed to be used for both chat...
bakllava                 BakLLaVA is a multimodal model consisting of the Mistral 7B bas...
codebooga                A high-performing code instruct model created by merging two ex...
codellama                A large language model that can use text prompts to generate an...
codeup                   Great code generation model based on Llama2.
```
Lists the available models from the ollama site along with the description

To see the available tags for a model but excludes the multitude of "tuning" tags

```bash
$ ollama-models alfred

All tags for alfred

Tag      Size
------   ----
latest   24GB
40b      24GB
```

To see all the tags

```bash
$ ollama-models alfred --all
All tags for alfred

Tag             Size
-------------   ----
latest          24GB
40b             24GB
40b-1023-q4_0   24GB
40b-1023-q4_1   26GB
40b-1023-q5_0   29GB
40b-1023-q5_1   32GB
40b-1023-q8_0   44GB
```
## ollama-update

Go over the already installed models and make sure they are up to date

## ollama-bench

A tool to benchmark ollama. It requires a config file

```yaml
models:
  - codellama:latest
  - llama2:latest
  - llava:latest
  - magicoder:latest
prompts:
  - Why is the sky blue?
  - You are an expert programmer that writes simple, concise code and explanations. Write a python function to generate the nth fibonacci number
server: http://localhost:11434
```

It assumes that the models has been installed and that the server is running

```bash
$ ollama-bench --config bench.yaml --report results.json
codellama:latest
    Why is the sky blue?
    You are an expert programmer that writes simple, concise code and explanations. Write a python function to generate the nth fibonacci number
llama2:latest
    Why is the sky blue?
    You are an expert programmer that writes simple, concise code and explanations. Write a python function to generate the nth fibonacci number
llava:latest
    Why is the sky blue?
    You are an expert programmer that writes simple, concise code and explanations. Write a python function to generate the nth fibonacci number
magicoder:latest
    Why is the sky blue?
    You are an expert programmer that writes simple, concise code and explanations. Write a python function to generate the nth fibonacci number
```
The config file is supplied with the `--config` option and the results written to the filename given with the `--report` option. The output is a weird serial JSON format


## ollama-dump

Dump a list of all the models and their tags and sizes as yaml
