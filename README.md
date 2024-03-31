# Read Me

<br/>

**Paper:** EMONA: Event-level Moral Opinions in News Articles<br/>
**Accepted:** The 2024 Annual Conference of the North American Chapter of the Association for Computational Linguistics (NAACL 2024)<br/>
**Authors:** Yuanyuan Lei, Md Messal Monem Miah, Ayesha Qamar, Sai Ramana Reddy, Jonathan Tong, Haotian Xu, Ruihong Huang<br/>
**Affiliation:** Department of Computer Science and Engineering, Texas A&M University, College Station, Texas, USA<br/>
**Paper Link:** paper link coming soon

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

The annotators were instructed to annotate a plain article in two passes, identifying event mentions and assigning moral labels for events. Therefore, each word in an article receives one of the following twelve labels: **non-event** (not an event mention), **non-moral** (an event mention without moral opinions), **care**, **harm**, **fairness**, **cheating**, **loyalty**, **betrayal**, **authority**, **subversion**, **purity**, **degradation**. The latter ten labels correspond to the ten moral foundations in Moral Foundation Theory. If a word is assigned the care label, it means that this word is an event mention that bears a moral opinion from care dimension. Similar for the other moral labels.

* **annotation_guideline.pdf**: We release the annotation guideline for the EMONA dataset.


<br/>

## Dataset Instruction

The released dataset contains the following six folders:

**moral_allsides_articles** folder: The articles text for the AllSides portion of the EMONA dataset. The txt file is named as _"allsides_topic_ideology_number.txt"_. For example, the file name _"allsides_elections_r_1.txt"_ means that the topic is elections and the article-level ideology provided by the AllSides dataset is right (r). There are three types of article-level ideology: left (l), center (c), and right (r).

**moral_allsides_annotations** folder: The annotations for the AllSides portion of the EMONA dataset.

* "media": the media outlet of the article
* "source": the dataset source of the article, which is "AllSides"
* "topic", "date", "ID", "url", "title", "num_sentences": the topic, date, id, url, title, and number of sentences of this article
* "article_level_bias": the annotations for article-level ideology provided by the AllSides dataset, including left (l), center (c), or right (r)
* "sentences": the annotations for event-level moral opinions provided by the EMONA dataset
  * "sentence_id": the id of this sentence
  * "sentence_start": the start character index of this sentence in the article txt file, the article txt file can be found in the articles folder
  * "sentence_end": the end character index of this sentence in the article txt file
  * "sentence_text": the text of this sentence
  * "tokens_list": the list of tokens, we use TreebankWordTokenizer() function in the nltk.tokenize package to tokenize the sentence
  * "tokens_label_list": the list of event-level moral labels for each token
  * "tokens_dicts_list": the list of detailed information for each token, "token" means the text of this token, "start_char" means the start character index of this token in the article txt file, "end_char" means the end character index of this token in the article txt file, "label" means the event-level moral label for this token. The corresponding article txt file can be found in the articles folder.

**moral_basil_articles** folder: The articles text for the BASIL portion of the EMONA dataset. The txt file is named as _"basil_triplet-id_media.txt"_. For example, the file name _"basil_3_nyt.txt"_ means that the triplet id is 3 and the media outlet is New York Times (nyt). There are three types of media outlets: Fox News (fox), New York Times (nyt), Huffington Post (hpo).

**moral_basil_annotations** folder: The annotations for the BASIL portion of the EMONA dataset.

* "uuid", "triplet-uuid": the id of article and the id of triplet provided by the BASIL dataset
* "media": the media outlet of the article, including Fox News (fox), New York Times (nyt), Huffington Post (hpo)
* "source": the dataset source of the article, which is "BASIL"
* "title", "date", "url", "num_sentences": the title, date, url, and number of sentences of this article
* "main-entities", "main-event": the main entities and the main event in the article annotated by the BASIL dataset
* "basil_title_annotations": the annotations for the article title provided by the BASIL dataset
* "basil_article_level_annotations": the annotations for article-level stance provided by the BASIL dataset
* "basil_sentence_level_annotations": the annotations for sentence-level media bias provided by the BASIL dataset
* "sentences": the annotations for event-level moral opinions provided by the EMONA dataset
  * "sentence_id": the id of this sentence
  * "sentence_start": the start character index of this sentence in the article txt file
  * "sentence_end": the end character index of this sentence in the article txt file
  * "sentence_text": the text of this sentence
  * "tokens_list": the list of tokens in this sentence
  * "tokens_label_list": the list of event-level moral labels for each token
  * "tokens_dicts_list": the list of detailed information for each token, including the text of this token, the start and end character index of this token in the article txt file, and the event-level moral label for this token
 
**moral_mpqa_articles** folder: The articles text for the MPQA 3.0 portion of the EMONA dataset.

**moral_mpqa_annotations** folder: The annotations for the MPQA 3.0 portion of the EMONA dataset.

* "doc_id": the document id in the MPQA 3.0 dataset
* "source": the dataset source of the article, which is "MPQA_3.0"
* "num_sentences": the number of sentence of this article
* "mpqa_sentence_level_annotations": the annotations for entity/event-level general opinions provided by the MPQA 3.0 dataset
  * "role_mentions": the role type of opinions, such as holder or target
  * "opinion_mentions": the polarity, trigger, and arguments of the opinion mentions
* "sentences": the annotations for event-level moral opinions provided by the EMONA dataset
  * "sentence_id": the id of this sentence
  * "sentence_start": the start character index of this sentence in the article txt file
  * "sentence_end": the end character index of this sentence in the article txt file
  * "sentence_text": the text of this sentence
  * "tokens_list": the list of tokens in this sentence
  * "tokens_label_list": the list of event-level moral labels for each token
  * "tokens_dicts_list": the list of detailed information for each token, including the text of this token, the start and end character index of this token in the article txt file, and the event-level moral label for this token




<br/>

## Citation

If you are going to cite this paper, please use the form:

Yuanyuan Lei, Md Messal Monem Miah, Ayesha Qamar, Sai Ramana Reddy, Jonathan Tong, Haotian Xu, and Ruihong Huang. 2024. EMONA: Event-level Moral Opinions in News Articles. In Proceedings of the 2024 Annual Conference of the North American Chapter of the Association for Computational Linguistics (NAACL), Mexico City, Mexico. Association for Computational Linguistics.


<br/>

## Reference

[1] Ramy Baly, Giovanni Da San Martino, James Glass, and Preslav Nakov. 2020. We can detect your bias: Predicting the political ideology of news articles. In Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP), pages 4982–4991, Online. Association for Computational Linguistics.<br/>

[2] Lisa Fan, Marshall White, Eva Sharma, Ruisi Su, Prafulla Kumar Choubey, Ruihong Huang, and Lu Wang. 2019. In plain sight: Media bias through the lens of factual reporting. In Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP), pages 6343–6349, Hong Kong, China. Association for Computational Linguistics.<br/>

[3] Lingjia Deng and Janyce Wiebe. 2015. MPQA 3.0: An entity/event-level sentiment corpus. In Proceedings of the 2015 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, pages 1323–1328, Denver, Colorado. Association for Computational Linguistics.<br/>
















