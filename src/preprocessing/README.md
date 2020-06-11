
This repo includes the dataset extraction and preprocessing scripts.

We construct three datasets for outline-conditioned generation. We focus on fictitious generation, but also include the news domain for generalization.  We build on existing publicly available datasets for the  target  narratives,  paired  with  automatically constructed input outlines as described in detail in our paper. Here we provide the dataset ids to and the preprocessing scripts to construct the train/validation/test splits for experimentation.

### Prerequisites

numpy

Rake

nltk

TfidfVectorizer

### WikiPlots

<a href="https://github.com/markriedl/WikiPlots">The Wikiplots corpus</a> consists of plots of movies, TV shows, and books scraped from Wikipedia. 
Please use the scripts provided in the link to extract the dataset. Then use the script <a href="./wikiplots_splits.txt">wikiplots_splits.txt</a> to construct the train, validation and text datasets that were used in the paper.


### WritingPrompts

This is a story generation dataset, presented in <a href="https://arxiv.org/abs/1805.04833">Hierarchical Neural Story Generation, Fan et.al., 2018</a> collected from the /r/WritingPrompts subreddit - a forum where Reddit users compose short stories inspired by other users’ prompts. It contains over 300k human-written (prompt, story) pairs. We use the same train/dev/test split from the original dataset paper.  


### New York Times

NYTimes, <a href="https://catalog.ldc.upenn.edu/LDC2008T19">The New York Times Annotated Corpus LDC2008T19</a>, contains news articles. 
We use the scripts to parse NYT corpus and then split into train, validation and test using the list of keys provided in <a href="./nyt_splits.txt">nyt_splits.txt</a>

Lastly, run the <a href="./extract_outlines.py">extract_outlines.py</a> to extract the outline-labeled documents that can be used as input to the train Plotmachines fine-tuning models. This script can extract the wikiplots data. 


### After Pre-Processing 

Once the files are generated, rename the preprocessed files as "[train|val|test]_encoded.jsonl". 
