# TODOs / next steps

- When simulating, add an argument new=True to check that a simulated word does not appear in the original text corpus
- Update ipynb in doc/ to remove the dev path (../..)
- Write some tests. Unit/Integration/..?
- Add the command line script back.
- Try developing a RESTful API to serve name suggestions.
- In [the docs](https://startup-name-generator.readthedocs.io/en/latest/modules.html#module-sng.wordlists.wordlists), why are my docstrings not marked with "Parameters:" and "Returns:" markers like [here](https://pomegranate.readthedocs.io/en/latest/HiddenMarkovModel.html#pomegranate.hmm.HiddenMarkovModel.add_transitions)?
- When using a stored model for simulation, I still need to load the wordlist in order to generate the character dictionary. The wordlist can not be changed, otherwise you'd have to retrain the model. It would be nice to store the character set (it's the `ix_to_char` dictionary in the code) along with the model.
- Since I'm not yet a Python expert, there are most likely some suboptimal ways of doing things in the code.
- I currently filter out the hyphen during preprocessing. Ideally, I should keep it if it appears within a word, and filter it if it represents something else like a bullet list item.
- It would be cool to have an option to specify that one input name should be one *line* instead of one word. Then, one could use lists of actual company names that include symbols like ampersands, whitespace, etc., and sample these as well. See [here](https://www.wordlab.com/archives/company-names-list) and [here](https://www.sec.gov/rules/other/4-460list.htm) for nice possible input lists.

## New Features

- word2vec to create two-part names, things like "DataVector" or "Data Matrix".
  - You could choose 2 words with a small distance
  - Or you get random suggestions, rate them with "like" or "hate" and converge to a good second word. E.g. "Data Zebra", if you've rated a few animals with "like".
