**[colab link](https://colab.research.google.com/drive/1B3-_WR_ge9Teea6tGzF-E5Hk44wCX_wk?usp=sharing)**

Note that we currently focus on two deep learning models: [Sbert](https://www.sbert.net/) and [BART (with no constraints)](https://ai.facebook.com/research/publications/bart-denoising-sequence-to-sequence-pre-training-for-natural-language-generation-translation-and-comprehension/)

For BART that I ran this afternoon:

To test what is going on inside the model, I made some simple modifications:
* I only put 10 sentences into the pre-trained model (output/reframer --  the pre-trained model you will generate when you run code on your own). I only want to reframe ten negative sentences using my pretrained model b/c it will save me lots of time. These ten sentences are in the CSV document: data/whole test CSV. Reframed text will be generated within the output folder, named "bart_unconstrained.txt"

The whole test data (instead 10 short sentences I use) is [here](https://github.com/SALT-NLP/positive-frames/blob/main/data/wholetest.csv); the reframed text data (whole) is in the output folder, named "bart_unconstrained_whole.txt"
* I suspect the process is first to tokenize both the original text and reframed text, then use the token id in the reframed text to replace the token id in the original text, and finally convert a list of lists of token ids into a list of strings by calling decode (Amit disagrees though :-)). I reviewed the text-generation method 'run.py' lines 120 and 121, they just attach all decoded token ids to a set of strings (sentence), so before each '\n' i added an indicator "stop" (see the colab link). That line of code will be 

```
decoded_preds_joined = ["\n stop".join(nltk.sent_tokenize(pred.strip())) for pred in decoded_preds]
```
Open to discussion.
