## Data
// - Detailed steps for processing of Gigaword dataset will be released soon.
### Step 1: Download the [Gigaword dataset](https://catalog.ldc.upenn.edu/ldc2011t07) (copyright requirement). 
- It consists of 7 files, afp_eng, apw_eng, cna_eng, ltw_eng, nyt_eng, wpb_eng, xin_eng.

| Source | #Files | Gzip-MB | Totl-MB | K-wrds  | #DOCs |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
|afp_eng	|146	|1732	 |4937	 |738322	|2479624 |
|apw_eng	|193	|2700	 |7889	 |1186955	|3107777|
| cna_eng	|144	|86	   |261	   |38491	  |145317|
| ltw_eng	|127	|651	 |1694	 |268088	|411032|
| nyt_eng	|197	|3280	 |8938	 |1422670	|1962178|
| wpb_eng	|12	  |42	   |111    |17462	  |26143|
| xin_eng	|191	|834	 |2518	 |360714	|1744025|
| TOTAL  	|1010	|9325	 |26348	 |4032686	|9876086|

- Note that in the #DOCs column, there are in total 9,876,086 documents. The following is example document released by the Gigaword official website:

![](https://github.com/code4conference/Data/blob/master/LDC2011T07.png)

- We specifically take the headline and the very first sentence as one instance, so theoretically we should have 9,876,086 instances. 

**Please note that each document corresponds to a id (in the example, doc ID: XIN_ENG_20100920.0459), and we will release corresponding label for these IDs instead of the first sentence due to the copyright.** 

### Step 2: Data Cleansing
- To exclude the effect of strange punctuations, we keep (sentence, headline) pair only if the sentence contains alphabet (a-z, A-Z), pause mark(","), stop mark(".") and "'s". 

- Filter out (sentence, headline) pairs if the length of sentence is less than 10 or over than 60. There is no need for sentence compression if the length is too short.

After step 2, one should yield around [1.02 million (sentence, headline) pairs](https://github.com/code4conference/Data/blob/master/1.02M%20sentences%20in%20Gigaword.txt)

### Human Annotated Data
- We ask human annotator to create [200 extractive compressions](https://github.com/code4conference/Data/blob/master/first%20200-sentences%20labels.txt) for the very first [200 sentences](https://github.com/code4conference/Data/blob/master/first%20200%20sentences.txt)

