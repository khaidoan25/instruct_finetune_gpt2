# instruct_finetune_gpt2
NLP702 Homework 2 - Instruct

# **Contribution Note: Checkout to new branch from `main` branch before doing anything, and submit a pull request.**

## Setup

Run the following command to pull the stanford_alpaca module, which is used to generate
dataset

```bash
git pull --recurse-submodules
git submodule update --recursive --remote
```

## Get dataset

### Subset of alpaca data

There are already a subset of 5k samples of alpaca data in the folder [./modules/stanford_alpaca/data](./modules/stanford_alpaca/data/). If you want to generate new subset, run

```bash
cd ./modules/stanford_alpaca
python -m generate_instruction generate_instruction_alpaca
```

### Generate new data with ChatGPT

Run

```bash
cd ./modules/stanford_alpaca
python -m generate_instruction generate_instruction_following_data
```

With this option, you need to pay for the ChatGPT API.

### Generate new data with GPT2

*In progress...*

## Finetune GPT

At first, you need to download the model to your local disk (in case you are using cluster).

Then `cd` in to `modules/stanford_alpaca` folder and set the environment variable `MODEL_PATH`.

```bash
export MODEL_PATH=<your_model_path>
```

Run the following commnand to start finetuning

```bash
bash finetune_gpt.sh
```