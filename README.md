# NLP
This repo will contain all information about NLP.</br>
The dataset is from http://ai.stanford.edu/~amaas/data/sentiment/ </br>
It is for sentiment analysis also known as text classification.

Below is the bash to combine positive reviews and negative reviews in train and test.</br>
After download movie_data.tar.gz, unzip it and run the below bash file.
```
#!/bin/bash

cd aclImdb
mkdir movie_data

# puts four files in the combined_files directory:
# full_train.txt, full_test.txt, original_train_ratings.txt, and original_test_ratings.txt
for split in train test;
do

  for sentiment in pos neg;
  do

    for file in $split/$sentiment/*;
    do
              cat $file >> movie_data/full_${split}.txt;
              echo >> movie_data/full_${split}.txt;

	     # This line adds files containing the original reviews if desired
             # echo $file | cut -d '_' -f 2 | cut -d "." -f 1 >> combined_files/original_${split}_ratings.txt;
    done;
  done;
done;
```
I give the data directory call movie_data which is the result of running the above bash code. I will use this dataset to do NLP learning and test.
