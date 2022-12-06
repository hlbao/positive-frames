**[colab link](https://colab.research.google.com/drive/1B3-_WR_ge9Teea6tGzF-E5Hk44wCX_wk?usp=sharing)**

Note that we currently focus on two deep learning models: [Sbert](https://www.sbert.net/) and [BART (with no constraints)](https://ai.facebook.com/research/publications/bart-denoising-sequence-to-sequence-pre-training-for-natural-language-generation-translation-and-comprehension/)

To test what is going on inside the model, I made two simple modifications:
* I only put 10 sentences into the pre-trained model (see output/reframer --  the pre-trained model you will generate); I only want to reframe ten negative sentences using my pretrained model. These ten sentences are within the CSV document: whole test data set. Reframed text will be generated within the output folder, named "bart_unconstrained.txt"
* The whole test data (instead 10 short sentences I use) is [here](https://github.com/SALT-NLP/positive-frames/blob/main/data/wholetest.csv); the reframed text data is in the output folder, named "bart_unconstrained_whole.txt"
* I suspect the process is first to tokenize both original text and reframed text, then use the token id in the reframed text to replace the token id in the original text, and finally convert a list of lists of token ids into a list of strings by calling decode, I review the generation method, 
