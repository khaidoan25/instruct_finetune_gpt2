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

*In progress...*

For this option, you need to prepare your own `my_seed_tasks.jsonl` and `my_prompt.txt`
files.

Run

```bash
cd ./modules/stanford_alpaca
python -m generate_instruction generate_instruction_following_data_gpt2
```

*Note*: the generated data of gpt2 is currently terrible, we cannot use it for finetuning.
The script above is just used for getting one example of generated text. You can see the 
result in the file [result.txt](./modules/standford_alpaca/result.txt).

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