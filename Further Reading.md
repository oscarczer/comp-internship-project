# How can QLoRA PEFT utilised to improve offline financial document generation with Llama 2 7B

#### What is LoRA?
Low Rank Adaptation (LoRA) is a form of Parameter Efficient Fine Tuning (PEFT) which works through taking a pre-existing, pre-trained model and "freezing" some of the weights before training the rest of it on a dataset representative of a specific domain. This allows for substantially better results within this domain without relying on having to retrain the entire model.

LoRA specifically works through taking the matrix representative of the parameters that are going to be trained and splitting it into two lower rank matrices. This allows for orders of magnitude fewer parameters to train while still allowing the for the training of all of the unfrozen parts of the model. To show the extent to which this reduces computation, consider the following example: 

If you have a 10000 x 10000 matrix representing the parameters that are needing to be trained, you end up with a matrix that contains 100 million elements, all of which need to be tweaked to find their optimal weight. By contrast, if you use LoRA with a rank of 8, you will instead have two matrices such that the first is 10000 x 8 and the second is 8 x 10000. When multiplied together, this still gives us the full 10000 x 10000 matrix but now only requires the training of 160000 parameters, or 0.016%. 

Using this strategy, we are left with lightweight "adaptors" that can be thought of as "hats" we can be put on a model to make it better at a specific task (at the cost of likely being worse at other tasks due to now being fit specifically for that). These hats can then be easily switched out and allow us to use the same base model with the capability of improving performance in different domains with ease. 
#### Quantization
Instead of just using the base model (which despite being relatively small is still unable to fit on a lot of smaller GPUs and was only just usable with the best GPU available on Google Colab) I primarily used a "quantized" version of the model. Quantization is the process of reducing the floating precision of the original model from 16 bits to 8 or 4 (in this case I choose 4). This affects the performance of the model however also substantially increases its speed and reduces its size (typically by the same factor that the precision is reduced by, i.e., the Llama 2 7B model goes from 13gb to ~3.2gb after 4bit quantization). 

I trained the adaptors on the 4 bit model however I then tested them on both the 4 bit and full precision models (in a process called Quantized LoRA or QLoRA). This allowed for low training times and low reliance on compute power but still gave noticeable results on both the quantized and full precision models.
#### Model Information
For the purpose of this research I have chosen to use the Llama 2 7B parameter model. This is because at the time of starting it was one of the best models around for its relatively small size, it is free and open source (including for commercial use) and it has a lot of tools available for fiddling with specific aspects of the model.
#### Dataset Information
##### GPT Dataset
This dataset was created through manual prompting of OpenAI's GPT 4. It required first generating one entry and then asking for the bot to generate more bit by bit. The process was slightly tedious as it could only create ~3 entries at a time however it created entries that were of very high quality and exactly what we wanted for the task. As GPT 4 is a much larger model than LLama 2 7B, the results that it could generate off the bat were substantially better and more importantly, good enough to act as a guide for the sort of documents the Llama model could strive to output. 

In the end this dataset ended up only being 100 entries which took maybe 2 hours to create. Actually training the adaptor with it only took about 5 minutes and it resulted in an adaptor that was 80mb (barely significant when comparing to the size of the models)
##### Full Dataset
This dataset was collated using a series of datasets available from the Hugging Face platform, a site for LLM researchers and hobbyists to share models and datasets in a collaborate, open source environment. Pieces of each of the following datasets were used 

- [FinGPT/fingpt-ner](https://huggingface.co/datasets/FinGPT/fingpt-ner)
- [FinGPT/fingpt-sentiment-train](https://huggingface.co/datasets/FinGPT/fingpt-sentiment-train)
- [FinGPT/fingpt-fiqa_qa](https://huggingface.co/datasets/FinGPT/fingpt-fiqa_qa)
- [zeroshot/twitter-financial-news-sentiment](https://huggingface.co/datasets/zeroshot/twitter-financial-news-sentiment)

And contains data based on financial sentiment, extracting financial information from prompts and general financial knowledge. The final dataset does not contain all of the entries from each of the above (which would be close to 100k) and instead reaches about 15k entires total. Training the adaptor with this took a bit over 2 hours and the size of said adaptor was somehow smaller at only 67.3mb

