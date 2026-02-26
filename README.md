# IronGPT: 10M Parameter Transformer from Scratch

Built a Decoder-only Transformer architecture entirely from scratch using pure PyTorch. No `transformers` library, no pre-trained weights. Just matrices, gradients, and raw math.

I am a 13-year-old AI researcher deeply interested in LLM architecture and AI Alignment. This is my implementation of the core engine behind models like GPT-3, built at the character level.

## Architecture Details
- **Type:** Autoregressive Language Model (Char-level)
- **Parameters:** ~10 Million
- **Layers:** 6 Transformer Blocks
- **Attention:** 6 Heads (64 features each, 384 embedding dim)
- **Context Window:** 256 tokens
- **Optimization:** AdamW (lr=3e-4), Cross-Entropy Loss

## Training Run
The model was trained on the English translation of Leo Tolstoy's *"War and Peace"* (~3.3 MB, 112 unique characters).
- **Hardware:** Google Cloud T4 GPU
- **Iterations:** 5,000
- **Final Loss:** 1.38 (Perplexity ~3.99)

## Generated Output
After 5000 steps, the model learned English grammar, Tolstoy's character names (Pierre, Prince Andrew), dialogue formatting, and punctuation from absolute scratch. 

Here is an unedited 1000-token generation sample (temperature=1.0):

> *"What it!" thought, of turning bentration questions, ordears his chers
belighted with his heart furent why ceented the dipsortion in the colder
kissed to Pierre. Coiclliar little to a succoun of Torme and spokene...
> “Every good something,” she aspemeant, “Oh, Dange Borís,”
> continued Pierre thing, while Prince Andrew that it sung that
> he’s eyes this own people dictions. It everything begin weat have closen.
> 
> Pierre noticed, having the way men for and able the daughter’n and kiss
> incons. You get great of youpeng it partrical now have joyfulling the
> ground offs, glassmer for Prally and whispings he lightly as sinn appeor an
> officer which he noisee continue the militiant was my dicked up for a
> so chard obtabing frightened troun ober to her many. But what had Pfull
> articis, and Annatole, which juiced him to be, a sing fear anbuder it
> nearing the now of One when itt a lies Moscow, as and kissed banet.

## What's Next?
Currently moving away from Char-level generation. The next step is implementing **Byte Pair Encoding (BPE)** to build a proper Tokenizer and compress the context window to train on code.
