# Read Me

<br/>

**Paper:** EMONA: Event-level Moral Opinions in News Articles<br/>
**Accepted:** The 2024 Annual Conference of the North American Chapter of the Association for Computational Linguistics (NAACL 2024)<br/>
**Authors:** Yuanyuan Lei, Md Messal Monem Miah, Ayesha Qamar, Sai Ramana Reddy, Jonathan Tong, Haotian Xu, Ruihong Huang<br/>
**Paper Link:** 

<br/>

## Dataset Overview

The EMONA dataset is the first dataset to annotate event-level moral opinions in news articles.

<br/>

## Dataset Sources

We intentionally select three different components to form our dataset. Overall, the dataset comprises 400 news articles, 10k sentences and 283k words.

* **AllSides** (Baly et al., 2020): provides article-level ideology stance labels: left, center, and right. We select 12 frequently discussed topics: abortion, coronavirus, elections, gun control, immigration, lgbt rights, race and racism, violence, politics, us house, us senate, white house. Each topic comprises five articles for each of the three stances, spanning from 2012 to 2020, resulting in a total of 180 articles.<br/>
* **BASIL** (Fan et al., 2019): provides sentence-level media bias labels and collects 100 triples of articles from three medias (Fox News, New York Times, Huffington Post) discussing the same event. We sample five triples for each year from 2010 to 2019, leading to 50 articles from each media and a total of 150 articles.<br/>
* **MPQA 3.0** (Deng and Wiebe, 2015): annotates general opinions towards entities and events for 70 articles from the years 2001 to 2002. We retained all 70 articles for the study of the correlation between event-level moral opinions and event-level general opinions.<br/>

<br/>

## Dataset Annotation

The annotators were instructed to annotate a plain article in two passes, identifying event mentions and assigning moral labels for events. Therefore, each word in an article receives one of the following twelve labels: **non-event** (not an event mention), **non-moral** (an event mention without moral opinions), **care**, **harm**, **fairness**, **cheating**, **loyalty**, **betrayal**, **authority**, **subversion**, **purity**, **degradation**. The latter ten labels correspond to the ten moral foundations in Moral Foundation Theory. If a word receives the care label, that means this word is an event mention that bears a moral opinion from care dimension. Similar for the other moral labels.

* **annotation_guideline.pdf**: we release the annotation guideline for the EMONA dataset.


<br/>

## Dataset Instruction


<br/>

## Citation

If you are going to cite this paper, please use the form:

Yuanyuan Lei, Md Messal Monem Miah, Ayesha Qamar, Sai Ramana Reddy, Jonathan Tong, Haotian Xu, and Ruihong Huang. 2024. EMONA: Event-level Moral Opinions in News Articles. In Proceedings of the 2024 Annual Conference of the North American Chapter of the Association for Computational Linguistics (NAACL), Mexico City, Mexico. Association for Computational Linguistics.


<br/>

## Reference

[1] Ramy Baly, Giovanni Da San Martino, James Glass, and Preslav Nakov. 2020. We can detect your bias: Predicting the political ideology of news articles. In Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP), pages 4982–4991, Online. Association for Computational Linguistics.<br/>

[2] Lisa Fan, Marshall White, Eva Sharma, Ruisi Su, Prafulla Kumar Choubey, Ruihong Huang, and Lu Wang. 2019. In plain sight: Media bias through the lens of factual reporting. In Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP), pages 6343–6349, Hong Kong, China. Association for Computational Linguistics.<br/>

[3] Lingjia Deng and Janyce Wiebe. 2015. MPQA 3.0: An entity/event-level sentiment corpus. In Proceedings of the 2015 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, pages 1323–1328, Denver, Colorado. Association for Computational Linguistics.<br/>
















