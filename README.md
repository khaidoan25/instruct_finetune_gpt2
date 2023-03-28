# instruct_finetune_gpt2
NLP702 Homework 2 - Instruct


## Setup

Run the following command to pull the stanford_alpaca module, which is used to generate
dataset

```bash
git pull --recurse-submodules
```

## Get dataset

### Subset of alpaca data

There are already a subset of 5k samples of alpaca data in the folder 
[./modules/stanford_alpaca/data]. If you want to generate new subset, run

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

In progress...