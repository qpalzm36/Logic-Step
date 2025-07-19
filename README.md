# Logic-Step
code for AAAI
Config:

python=3.10

pip install openai pandas jsonlines scikit-learn numpy

pip install accelerate matplotlib seaborn tqdm pyarrow

pip install torch transformers sentence-transformers

pip install einops transformers_stream_generator

pip install tiktoken faiss-cpu datasets peft

pip install vllm

retriever: fine-tune bge-en-v1.5  
finetuned model can be stored in "/data/yangcheng/aaai/retriever_finetuned"

generator: fine-tune Qwen-2.5-3B-Instruct,Qwen2.5-Math-7B-Instruct,,Meta-Llama3-8B-Instruct,Llama-2-7b-chat-hf
fintuned model can be stored in:
"/data/yangcheng/aaai/generator_finetuned/Qwen-2.5-3B-Instruct"
"/data/yangcheng/aaai/generator_finetuned/Qwen2.5-Math-7B-Instruct"
"/data/yangcheng/aaai/generator_finetuned/Meta-Llama-3-8B-Instruct"
"/data/yangcheng/aaai/generator_finetuned/Llama-2-7b-chat-hf"

Command:
nohup python 3_finetune_retriever.py > 3_finetune_retriever16.log 2>&1 &
nohup python 6_build_generator_data.py > 6_build_generator_data.log 2>&1 &
nohup python 7_finetune_generator2.py > 7_finetune_generator2.log 2>&1 &
nohup python 7_finetune_generatorllama2_7B.py > 7_finetune_generatorllama2_7B.log 2>&1 &
nohup python 7_finetune_generatorllama3_8B.py > 7_finetune_generatorllama3_8B.log 2>&1 &
nohup python 7_finetune_generatorqwne7B.py > 7_finetune_generatorqwen7B.log 2>&1 &

The file path that may need to be modified：
3_finetune_retriever.py:
default="/data/yangcheng/aaai/data/traindata/retrieverdata/retriever_training_data.jsonl" //37th row
default="/data/yangcheng/aaai/retriever_finetuned" //49th row
