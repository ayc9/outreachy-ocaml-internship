## Week 7: 2022-01-17 to 2022-01-21

Week 7 continues the parallel efforts for `make` and `eq`.

### Mentors' call

On this call, I expressed that I needed help understanding all the new code (optionals in `ppx_deriving` and `ppx_make`, new derivers `eq` and `compare`). In response, Sonja proposed the following break down for the upcoming weeks:
- In the short term 
    - **Step 1:** From JaneStreet's implementation, extract the signature code for `eq` into a new file in our repo, and make it work on its own. _(Should take half a day)_
    - **Step 2:** Same as above for `compare`'s signature code. _(Also half a day)_
    - **Step 3 and 4:** Repeat steps 1 and 2 for the structure code of `eq` and `compare` respectively. _(Half a day each)_
    - Finally, aim to finish signature half of work, **steps 1 and 2, by the end of week 7**.
- In the long term, time-allowing, after completing `make`, `eq` and `compare`, we might pick a deriver that doesn't already have a `ppxlib`-based implementation, in order to write a whole deriver from scratch!

We also agreed on keeping up the work for both derivers in parallel, as to keep advancing on `eq`, even as `make` is not fully completed yet, with a couple missing features (see [week 6 report](/weekly/week-6.md)). Sonja also shared [this issue](https://github.com/bn-d/ppx_make/issues/6) she created on the `ppx_make` repo, in an effort to connect with its author.

We also discussed the points brought up in the latest email from Outreachy. It covered reviewing the internship timeline as proposed in the first week, as well as many blog post ideas. I will probably write a blog post that is either a follow-up to the first blog, or a post on the unexpected complexity of `make`.

### Pairing 
