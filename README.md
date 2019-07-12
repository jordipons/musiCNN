# musiCNN
Pronounced as "musician", musiCNN is a set of pre-trained deep neural networks for music audio tagging.

Check the [documentation](https://github.com/jordipons/musiCNN/blob/master/DOCUMENTATION.md) and some [basic](https://github.com/jordipons/musiCNN/blob/master/basic%20example.ipynb) / [advanced](https://github.com/jordipons/musiCNN/blob/master/advanced%20example.ipynb) examples for additional ideas on how to use `musiCNN`.

Do you have questions? Check the [FAQs](https://github.com/jordipons/musiCNN/blob/master/FAQs.md).

## Installation
``` git clone https://github.com/jordipons/musiCNN.git```

``` pip install numpy librosa tqdm ```

```pip install tensorflow``` or ```pip install tensorflow-gpu``` (if you have a GPU)

## Run

From within python, you can estimate the topN tags:
~~~~python
from musiCNN.tagger import top_tags
top_tags('./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3', model='MTT', topN=10)
~~~~
>['techno', 'electronic', 'synth', 'fast', 'beat', 'drums', 'no vocals', 'no vocal', 'dance', 'ambient']

~~~~python
top_tags('./audio/TRWJAZW128F42760DD_test.mp3', model='MTT', topN=3)
~~~~
>['guitar', 'piano', 'fast']

or to compute the taggram (see the basic example for more details on how to depict it):

~~~~python
from musiCNN.extractor import extractor
taggram, tags = extractor('./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3', model='MTT')
~~~~
![Taggram](./images/taggram.png "Taggram")

These two music clips are included in the `./audio/` folder of this repository. 

You can listen to those and evaluate `musiCNN` yourself!
