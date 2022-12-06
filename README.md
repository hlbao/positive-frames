**[colab link](https://colab.research.google.com/drive/1B3-_WR_ge9Teea6tGzF-E5Hk44wCX_wk?usp=sharing)**

note that we currenly focus on two deep learning models: [Sbert](https://www.sbert.net/) and   [BART (with no constraints)](https://ai.facebook.com/research/publications/bart-denoising-sequence-to-sequence-pre-training-for-natural-language-generation-translation-and-comprehension/)

To test what's going on inside the model, I made two simple modification:
* I only put 10 sentences into pre-trained model (see output/reframer --  the pretrained model you will generate), I only want to reframe 10 negative sentences using my pretrained model. These 10 sentences are within the csv document: whole test data set. reframed text will be generated within the output folder, named with "bart_unconstrained.txt"
* 
