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

## ollama-dump

Dump a list of all the models and their tags and sizes as yaml
