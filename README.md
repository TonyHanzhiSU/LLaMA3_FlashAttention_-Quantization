# LLaMA3_FlashAttention_-Quantization
Final project for NYU Tandon ECE-GY 9143 HPML

The gaol is to optimize the LLaMA 3 model through the integration of the Flash-Attention and quantization so that it can be run in local device with limited recource. 

## Project milestones


Research and Initial Setup --_COMPLETED_
- Choose LLaMA 3 8B-instruct Model.
- Read all the documentations of LLaMA, transformers, Flash Attention, PEFT (Parameter-Efficient Fine-Tuning)
- Set up the develpment Environment
   
Integration of Flash-Attention --_COMPLETED_
- TODO

Quantization Implementation --_COMPLETED_
- TODO

Evaluation and Benchmarking --_COMPLETED_
- TODO
    
## Description of the repository and code structure

Since I don't have Nvidia GPU on my laptop, I used Google Colab for the Project. All the code and description is in the notebook.
-   `README.md`
	Project documentation
- `LLaMA_3_with_Flash_Attention_and_Quantization`
  The notebook contains all the code

	
## Example commands to execute the code

Open the Notebook via Google Colab or your local jupyter notebook if you have Nvidia GPU

1. Download the notebook from BERT/evaluate.ipynb 
2. Start the notebook server from the command line/terminal with command `jupyter notebook`
3. Run the notebook


## Results and observations

**Summary of Main Results**

Model Inference
The improvement using Flash attention 2 is not obvious for my two case input sequence length. In fact, it took longer to inference with Flash attention 2. However, according the report from Hugging Face, they concluded that Flash attention can achieve at most 1.9 speed up. I will conduct more study on that.

Model Fine Tuning
The improvement with Flash attention 2 is noticeable even with a small dataset and small epochs. The training time decrease from 20.67 to 19.57. A much better result compared to the model inference. Also, the usage of quantization with QLoRa is the most significant as it allows me to load the LLaMA 3 model into a L4 GPT which is unable to train the full precision LLaMA 3 in the first place. 


Without Flash Attention and 4 bits Quantization
- short input
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)

- long input
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)

With Flash Attention and 4 bits Quantization
- short input
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)

- long input
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)

Fine tunine with QLoRA 
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)

Fine tunine with QLoRA and Flash Attention
![image](https://github.com/TonyHanzhiSU/LLaMA3_FlashAttention_-Quantization/imgs/)
