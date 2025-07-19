# Logic-Step
code for AAAI
**Config**</br>
python=3.10</br>
pip install openai pandas jsonlines scikit-learn numpy</br>
pip install accelerate matplotlib seaborn tqdm pyarrow</br>
pip install torch transformers sentence-transformers</br>
pip install einops transformers_stream_generator</br>
pip install tiktoken faiss-cpu datasets peft</br>
pip install vllm</br>

**retriever**:fine-tune bge-en-v1.5</br>
finetuned model can be stored in "/data/yangcheng/aaai/retriever_finetuned"</br>

**generator**:fine-tune Qwen-2.5-3B-Instruct,Qwen2.5-Math-7B-Instruct,,Meta-Llama3-8B-Instruct,Llama-2-7b-chat-hf</br>
fintuned model can be stored in:</br>
"/data/yangcheng/aaai/generator_finetuned/Qwen-2.5-3B-Instruct"</br>
"/data/yangcheng/aaai/generator_finetuned/Qwen2.5-Math-7B-Instruct"</br>
"/data/yangcheng/aaai/generator_finetuned/Meta-Llama-3-8B-Instruct"</br>
"/data/yangcheng/aaai/generator_finetuned/Llama-2-7b-chat-hf"</br>

**Command**</br>
nohup python 3_finetune_retriever.py > 3_finetune_retriever16.log 2>&1 &</br>
nohup python 6_build_generator_data.py > 6_build_generator_data.log 2>&1 &</br>
nohup python 7_finetune_generator2.py > 7_finetune_generator2.log 2>&1 &</br>
nohup python 7_finetune_generatorllama2_7B.py > 7_finetune_generatorllama2_7B.log 2>&1 &</br>
nohup python 7_finetune_generatorllama3_8B.py > 7_finetune_generatorllama3_8B.log 2>&1 &</br>
nohup python 7_finetune_generatorqwne7B.py > 7_finetune_generatorqwen7B.log 2>&1 &</br>

**The file path that may need to be modified**</br>
**3_finetune_retriever.py**:</br>
default="/data/yangcheng/aaai/data/traindata/retrieverdata/retriever_training_data.jsonl" //37th row</br>
default="/data/yangcheng/aaai/retriever_finetuned" //49th row</br>
