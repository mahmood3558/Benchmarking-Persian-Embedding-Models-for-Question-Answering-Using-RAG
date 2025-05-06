# Benchmarking Persian Embedding Models for Question-Answering Using RAG

## Overview
This repository provides the source code, data, and results from our paper *Benchmarking Persian Embedding Models for Question-Answering Using RAG*. Our research evaluates 17 Persian embedding models in a Retrieval-Augmented Generation (RAG) framework for question-answering tasks. This work aims to improve question-answering accuracy for Persian language models by testing their performance on datasets.

## Abstract
The rise of chatbots and large language models (LLMs) in Persian NLP has exposed limitations in accuracy and relevancy. To address these, our study evaluates the effectiveness of Retrieval-Augmented Generation (RAG) for question-answering, comparing 17 embedding models on four datasets (PersianQA, PersianQuAD, SQuAD, BoolQ). Our results highlight the top-performing models and measure their retrieval accuracy using hit@1, hit@3, hit@5, and hit@10 metrics.

## Repository Structure
- `datasets/`: Contains the four datasets used in this study:
  - **PersianQA**: Derived from Persian Wikipedia articles, inspired by SQuAD2.0.[Link](https://github.com/sajjjadayobi/PersianQA)
  - **PersianQuAD**: 1,000 question-context pairs developed by native speakers.[Link](https://github.com/BigData-IsfahanUni/PersianQuAD)
  - **SQuAD (translated)**: Persian translation of the English SQuAD dataset.
  - **BoolQ (translated)**: Persian translation of Google’s BoolQ yes/no dataset.

- `models/`: Code and configurations for the 17 embedding models, including:
  - HooshvareLab's BERT variations
  - Persian-Sentence-Transformer-News-Wiki-Pairs-v3
  - MiniLM, LaBSE, and others

## Results


##  performance of different models on various datasets by faiss (in percentage)

|Model|Dataset|Tok 1|Tok 3|Tok 5|Tok 10|
|:----|:----|:----|:----|:----|:----|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|pqa|90.75268817|95.91397849|97.09677419|98.49462366|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|PersianQuAD|88.1|95.5|97.1|98.7|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|SQuAD|47.1333964|65.56291391|72.85714286|81.60832545|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|BoolQ|55.04587156|73.21100917|79.6941896|85.50458716|
|HooshvareLab/bert-fa-base-uncased|pqa|62.79569892|82.90322581|88.92473118|94.08602151|
|HooshvareLab/bert-fa-base-uncased|PersianQuAD|70.9|86.6|91.5|95.2|
|HooshvareLab/bert-fa-base-uncased|SQuAD|18.51466414|31.90160833|39.51750237|49.56480605|
|HooshvareLab/bert-fa-base-uncased|BoolQ|13.24159021|22.72171254|27.6146789|35.62691131|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|pqa|29.03225806|50.43010753|62.68817204|77.52688172|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|PersianQuAD|49.7|79.3|86.8|94.3|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|SQuAD|7.057710501|14.17218543|18.09839167|25.28855251|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|BoolQ|6.20795107|11.31498471|14.7706422|19.05198777|
|HooshvareLab/bert-fa-zwnj-base|pqa|61.93548387|81.93548387|87.84946237|92.90322581|
|HooshvareLab/bert-fa-zwnj-base|PersianQuAD|75.8|88.4|92.3|95.3|
|HooshvareLab/bert-fa-zwnj-base|SQuAD|17.52128666|31.07852412|38.16461684|48.88363292|
|HooshvareLab/bert-fa-zwnj-base|BoolQ|10.70336391|20.55045872|26.05504587|34.89296636|
|HooshvareLab/roberta-fa-zwnj-base|pqa|49.78494624|68.17204301|75.37634409|83.97849462|
|HooshvareLab/roberta-fa-zwnj-base|PersianQuAD|65.9|85|91.5|97|
|HooshvareLab/roberta-fa-zwnj-base|SQuAD|14.0397351|24.61684011|31.28666036|40.66225166|
|HooshvareLab/roberta-fa-zwnj-base|BoolQ|10.06116208|17.88990826|22.04892966|29.32721713|
|sentence-transformers/paraphrase-MiniLM-L6-v2|pqa|8.924731183|16.66666667|21.82795699|32.04301075|
|sentence-transformers/paraphrase-MiniLM-L6-v2|PersianQuAD|13.3|26.1|34.3|45|
|sentence-transformers/paraphrase-MiniLM-L6-v2|SQuAD|2.251655629|3.557237465|4.389782403|6.263008515|
|sentence-transformers/paraphrase-MiniLM-L6-v2|BoolQ|1.009174312|1.804281346|2.140672783|2.752293578|
|sentence-transformers/all-MiniLM-L12-v2|pqa|6.021505376|13.11827957|20.21505376|28.38709677|
|sentence-transformers/all-MiniLM-L12-v2|PersianQuAD|14.5|26.5|34.1|50.4|
|sentence-transformers/all-MiniLM-L12-v2|SQuAD|3.528855251|5.383159886|6.868495743|9.072847682|
|sentence-transformers/all-MiniLM-L12-v2|BoolQ|3.241590214|4.98470948|6.29969419|7.798165138|
|sentence-transformers/all-MiniLM-L6-v2|pqa|3.978494624|9.35483871|12.90322581|22.15053763|
|sentence-transformers/all-MiniLM-L6-v2|PersianQuAD|7.1|22.3|34|51|
|sentence-transformers/all-MiniLM-L6-v2|SQuAD|0.510879849|1.106906339|1.485335856|2.308420057|
|sentence-transformers/all-MiniLM-L6-v2|BoolQ|1.009174312|1.559633028|1.957186544|2.5382263|
|sentence-transformers/all-mpnet-base-v2|pqa|6.129032258|14.19354839|18.60215054|26.98924731|
|sentence-transformers/all-mpnet-base-v2|PersianQuAD|8.6|14.5|26.8|48.7|
|sentence-transformers/all-mpnet-base-v2|SQuAD|2.724692526|4.749290445|5.799432356|7.852412488|
|sentence-transformers/all-mpnet-base-v2|BoolQ|2.5382263|3.73088685|4.525993884|5.168195719|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|pqa|72.15053763|84.19354839|88.06451613|92.58064516|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|PersianQuAD|73|86.5|91.2|96.5|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|SQuAD|38.18353832|55.30747398|62.58278146|71.81646168|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|BoolQ|39.8470948|57.70642202|63.60856269|71.43730887|
|sentence-transformers/distiluse-base-multilingual-cased-v1|pqa|34.51612903|50.75268817|59.03225806|68.17204301|
|sentence-transformers/distiluse-base-multilingual-cased-v1|PersianQuAD|44.9|60.8|69.1|81.5|
|sentence-transformers/distiluse-base-multilingual-cased-v1|SQuAD|12.75307474|20.97445601|25.67644276|32.42194891|
|sentence-transformers/distiluse-base-multilingual-cased-v1|BoolQ|10.42813456|17.6146789|20.76452599|25.87155963|
|sentence-transformers/distiluse-base-multilingual-cased-v2|pqa|60.86021505|79.03225806|85.48387097|91.39784946|
|sentence-transformers/distiluse-base-multilingual-cased-v2|PersianQuAD|70.2|85.4|89.2|94.7|
|sentence-transformers/distiluse-base-multilingual-cased-v2|SQuAD|36.44276254|53.90728477|61.11636708|70.69063387|
|sentence-transformers/distiluse-base-multilingual-cased-v2|BoolQ|34.58715596|52.81345566|59.8470948|68.71559633|
|sentence-transformers/LaBSE|pqa|80.53763441|91.1827957|93.87096774|96.23655914|
|sentence-transformers/LaBSE|PersianQuAD|79.3|90.8|94.1|96.3|
|sentence-transformers/LaBSE|SQuAD|39.3755913|56.93472091|64.44654683|74.15326395|
|sentence-transformers/LaBSE|BoolQ|34.40366972|50.79510703|57.12538226|66.05504587|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|pqa|41.61290323|59.03225806|66.34408602|77.74193548|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|PersianQuAD|50.7|67.9|76.8|88.7|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|SQuAD|13.62346263|25.51561022|31.80700095|41.82592242|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|BoolQ|13.36391437|23.48623853|27.67584098|34.00611621|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|pqa|60.32258065|80.53763441|87.74193548|93.5483871|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|PersianQuAD|64.4|82.1|90.3|94.9|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|SQuAD|23.140965|38.05108798|46.3103122|56.66982025|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|BoolQ|20.36697248|33.57798165|39.44954128|48.13455657|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|pqa|58.38709677|75.37634409|81.39784946|88.8172043|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|PersianQuAD|67.9|86.6|93.2|97.9|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|SQuAD|21.34342479|35.05203406|42.26111637|52.56385998|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|BoolQ|19.35779817|31.19266055|36.05504587|43.88379205|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|pqa|17.6344086|34.62365591|42.79569892|56.88172043|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|PersianQuAD|41.5|59.4|68.1|77.7|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|SQuAD|8.107852412|13.86944182|17.62535478|23.59508042|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|BoolQ|4.006116208|7.52293578|9.93883792|13.97553517|

**Note:** The above table provides hit@k results using faiss on four datasets (PersianQA, PersianQuAD, SQuAD, BoolQ).

---


##  performance of different models on various datasets by cosine similarity (in percentage)

|Model|Dataset|Tok 1|Tok 3|Tok 5|Tok 10|
|:----|:----|:----|:----|:----|:----|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|pqa|90.75268817|95.91397849|97.09677419|98.49462366|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|PersianQuAD|88.1|95.5|97.1|98.7|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|SQuAD|47.1333964|65.56291391|72.85714286|81.60832545|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|BoolQ|55.04587156|73.36391437|79.44954128|85.47400612|
|HooshvareLab/bert-fa-base-uncased|pqa|62.79569892|82.90322581|88.92473118|94.08602151|
|HooshvareLab/bert-fa-base-uncased|PersianQuAD|70.9|86.6|91.5|95.2|
|HooshvareLab/bert-fa-base-uncased|SQuAD|18.51466414|31.90160833|39.51750237|49.56480605|
|HooshvareLab/bert-fa-base-uncased|BoolQ|13.24159021|22.72171254|27.73700306|35.41284404|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|pqa|29.03225806|50.43010753|62.68817204|77.52688172|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|PersianQuAD|49.7|79.3|86.8|94.3|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|SQuAD|7.057710501|14.17218543|18.09839167|25.28855251|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|BoolQ|6.20795107|11.34556575|14.7706422|19.08256881|
|HooshvareLab/bert-fa-zwnj-base|pqa|61.93548387|81.93548387|87.84946237|92.90322581|
|HooshvareLab/bert-fa-zwnj-base|PersianQuAD|75.8|88.4|92.3|95.3|
|HooshvareLab/bert-fa-zwnj-base|SQuAD|17.52128666|31.07852412|38.16461684|48.88363292|
|HooshvareLab/bert-fa-zwnj-base|BoolQ|10.70336391|20.48929664|26.20795107|34.9235474|
|HooshvareLab/roberta-fa-zwnj-base|pqa|49.78494624|68.17204301|75.37634409|83.97849462|
|HooshvareLab/roberta-fa-zwnj-base|PersianQuAD|65.9|85|91.5|97|
|HooshvareLab/roberta-fa-zwnj-base|SQuAD|14.0397351|24.61684011|31.28666036|40.66225166|
|HooshvareLab/roberta-fa-zwnj-base|BoolQ|10.09174312|17.9204893|22.01834862|29.3883792|
|sentence-transformers/paraphrase-MiniLM-L6-v2|pqa|8.924731183|16.66666667|21.82795699|32.04301075|
|sentence-transformers/paraphrase-MiniLM-L6-v2|PersianQuAD|13.3|26.1|34.3|45|
|sentence-transformers/paraphrase-MiniLM-L6-v2|SQuAD|2.251655629|3.557237465|4.389782403|6.263008515|
|sentence-transformers/paraphrase-MiniLM-L6-v2|BoolQ|1.009174312|1.804281346|2.140672783|2.752293578|
|sentence-transformers/all-MiniLM-L12-v2|pqa|6.021505376|13.11827957|20.21505376|28.38709677|
|sentence-transformers/all-MiniLM-L12-v2|PersianQuAD|14.5|26.5|34.1|50.4|
|sentence-transformers/all-MiniLM-L12-v2|SQuAD|3.528855251|5.383159886|6.868495743|9.072847682|
|sentence-transformers/all-MiniLM-L12-v2|BoolQ|3.241590214|4.98470948|6.29969419|7.798165138|
|sentence-transformers/all-MiniLM-L6-v2|pqa|3.978494624|9.35483871|12.90322581|22.15053763|
|sentence-transformers/all-MiniLM-L6-v2|PersianQuAD|7.1|22.3|34|51|
|sentence-transformers/all-MiniLM-L6-v2|SQuAD|0.510879849|1.106906339|1.485335856|2.308420057|
|sentence-transformers/all-MiniLM-L6-v2|BoolQ|1.009174312|1.559633028|1.957186544|2.5382263|
|sentence-transformers/all-mpnet-base-v2|pqa|6.129032258|14.19354839|18.60215054|26.98924731|
|sentence-transformers/all-mpnet-base-v2|PersianQuAD|8.6|14.5|26.8|48.7|
|sentence-transformers/all-mpnet-base-v2|SQuAD|2.724692526|4.749290445|5.799432356|7.852412488|
|sentence-transformers/all-mpnet-base-v2|BoolQ|2.5382263|3.73088685|4.525993884|5.168195719|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|pqa|72.15053763|84.19354839|88.06451613|92.58064516|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|PersianQuAD|73|86.5|91.2|96.5|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|SQuAD|38.18353832|55.30747398|62.58278146|71.81646168|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|BoolQ|39.8470948|57.7675841|63.51681957|71.40672783|
|sentence-transformers/distiluse-base-multilingual-cased-v1|pqa|34.51612903|50.75268817|59.03225806|68.17204301|
|sentence-transformers/distiluse-base-multilingual-cased-v1|PersianQuAD|44.9|60.8|69.1|81.5|
|sentence-transformers/distiluse-base-multilingual-cased-v1|SQuAD|12.75307474|20.97445601|25.67644276|32.42194891|
|sentence-transformers/distiluse-base-multilingual-cased-v1|BoolQ|10.39755352|17.4617737|20.73394495|25.84097859|
|sentence-transformers/distiluse-base-multilingual-cased-v2|pqa|60.86021505|79.03225806|85.48387097|91.39784946|
|sentence-transformers/distiluse-base-multilingual-cased-v2|PersianQuAD|70.2|85.4|89.2|94.7|
|sentence-transformers/distiluse-base-multilingual-cased-v2|SQuAD|36.44276254|53.90728477|61.11636708|70.69063387|
|sentence-transformers/distiluse-base-multilingual-cased-v2|BoolQ|34.64831804|52.62996942|59.75535168|68.68501529|
|sentence-transformers/LaBSE|pqa|80.53763441|91.1827957|93.87096774|96.23655914|
|sentence-transformers/LaBSE|PersianQuAD|79.3|90.8|94.1|96.3|
|sentence-transformers/LaBSE|SQuAD|39.3755913|56.93472091|64.44654683|74.15326395|
|sentence-transformers/LaBSE|BoolQ|34.40366972|50.79510703|57.21712538|65.99388379|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|pqa|41.61290323|59.03225806|66.34408602|77.74193548|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|PersianQuAD|50.7|67.9|76.8|88.7|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|SQuAD|13.62346263|25.51561022|31.80700095|41.82592242|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|BoolQ|13.36391437|23.33333333|27.55351682|33.97553517|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|pqa|60.32258065|80.53763441|87.74193548|93.5483871|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|PersianQuAD|64.4|82.1|90.3|94.9|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|SQuAD|23.140965|38.05108798|46.3103122|56.66982025|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|BoolQ|20.33639144|33.54740061|39.48012232|48.10397554|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|pqa|58.38709677|75.37634409|81.39784946|88.8172043|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|PersianQuAD|67.9|86.6|93.2|97.9|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|SQuAD|21.34342479|35.05203406|42.26111637|52.56385998|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|BoolQ|19.35779817|31.40672783|36.26911315|43.88379205|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|pqa|17.6344086|34.62365591|42.79569892|56.88172043|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|PersianQuAD|41.5|59.4|68.1|77.7|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|SQuAD|8.107852412|8.107852412|17.62535478|23.59508042|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|BoolQ|4.006116208|7.4617737|9.93883792|13.91437309|

**Note:** The above table provides hit@k results using cosine similarity on four datasets (PersianQA, PersianQuAD, SQuAD, BoolQ).

---

##  performance of different models on various datasets by dot product (in percentage)

|Model|Dataset|Tok 1|Tok 3|Tok 5|Tok 10|
|:----|:----|:----|:----|:----|:----|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|pqa|90.53763441|95.80645161|97.20430108|98.49462366|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|PersianQuAD|88.3|95.4|97.3|98.7|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|SQuAD|46.62251656|65.14664144|72.65846736|81.28666036|
|ahdsoft/persian-sentence-transformer-news-wiki-pairs-v3|BoolQ|54.43425076|72.78287462|79.23547401|85.44342508|
|HooshvareLab/bert-fa-base-uncased|pqa|56.66666667|79.78494624|86.98924731|93.33333333|
|HooshvareLab/bert-fa-base-uncased|PersianQuAD|49.3|71|80.2|91.2|
|HooshvareLab/bert-fa-base-uncased|SQuAD|8.344370861|16.54683065|22.10028382|30.81362346|
|HooshvareLab/bert-fa-base-uncased|BoolQ|4.311926606|9.694189602|12.59938838|18.59327217|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|pqa|17.95698925|39.78494624|51.72043011|74.08602151|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|PersianQuAD|36.2|68.6|83|94.3|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|SQuAD|2.970671712|7.010406812|9.772942289|15.2128666|
|HooshvareLab/bert-fa-base-uncased-clf-persiannews|BoolQ|1.926605505|4.862385321|6.941896024|10.48929664|
|HooshvareLab/bert-fa-zwnj-base|pqa|55.16129032|77.09677419|83.97849462|91.82795699|
|HooshvareLab/bert-fa-zwnj-base|PersianQuAD|63.6|82.6|88.3|94.6|
|HooshvareLab/bert-fa-zwnj-base|SQuAD|4.105960265|10.10406812|15.07095553|24.62630085|
|HooshvareLab/bert-fa-zwnj-base|BoolQ|2.415902141|5.259938838|7.52293578|11.52905199|
|HooshvareLab/roberta-fa-zwnj-base|pqa|48.8172043|67.74193548|76.23655914|84.30107527|
|HooshvareLab/roberta-fa-zwnj-base|PersianQuAD|56.5|81|88.4|95.3|
|HooshvareLab/roberta-fa-zwnj-base|SQuAD|5.591296121|12.62062441|17.19962157|25.78051088|
|HooshvareLab/roberta-fa-zwnj-base|BoolQ|3.76146789|7.155963303|9.174311927|13.05810398|
|sentence-transformers/paraphrase-MiniLM-L6-v2|pqa|5.053763441|9.569892473|13.97849462|23.65591398|
|sentence-transformers/paraphrase-MiniLM-L6-v2|PersianQuAD|7.9|15.4|21.7|36.7|
|sentence-transformers/paraphrase-MiniLM-L6-v2|SQuAD|1.296121097|2.138126774|2.98013245|4.323557237|
|sentence-transformers/paraphrase-MiniLM-L6-v2|BoolQ|0.948012232|1.743119266|2.262996942|3.027522936|
|sentence-transformers/all-MiniLM-L12-v2|pqa|6.021505376|13.11827957|20.21505376|28.38709677|
|sentence-transformers/all-MiniLM-L12-v2|PersianQuAD|14.5|26.5|34.1|50.4|
|sentence-transformers/all-MiniLM-L12-v2|SQuAD|3.528855251|5.383159886|6.868495743|9.072847682|
|sentence-transformers/all-MiniLM-L12-v2|BoolQ|3.241590214|4.923547401|6.26911315|7.767584098|
|sentence-transformers/all-MiniLM-L6-v2|pqa|3.978494624|9.35483871|12.90322581|22.15053763|
|sentence-transformers/all-MiniLM-L6-v2|PersianQuAD|7.1|22.3|34|51|
|sentence-transformers/all-MiniLM-L6-v2|SQuAD|0.510879849|1.106906339|1.485335856|2.308420057|
|sentence-transformers/all-MiniLM-L6-v2|BoolQ|1.009174312|1.559633028|1.957186544|2.5382263|
|sentence-transformers/all-mpnet-base-v2|pqa|6.129032258|14.19354839|18.60215054|26.98924731|
|sentence-transformers/all-mpnet-base-v2|PersianQuAD|8.6|14.5|26.8|48.7|
|sentence-transformers/all-mpnet-base-v2|SQuAD|2.724692526|4.749290445|5.799432356|7.852412488|
|sentence-transformers/all-mpnet-base-v2|BoolQ|2.5382263|3.73088685|4.525993884|5.168195719|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|pqa|67.95698925|84.19354839|87.95698925|92.25806452|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|PersianQuAD|68.1|86.1|91.8|96.6|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|SQuAD|33.19772942|51.10690634|58.81740776|68.59035005|
|sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2|BoolQ|33.02752294|51.59021407|58.96024465|68.16513761|
|sentence-transformers/distiluse-base-multilingual-cased-v1|pqa|34.94623656|49.67741935|56.88172043|66.23655914|
|sentence-transformers/distiluse-base-multilingual-cased-v1|PersianQuAD|41.1|57.7|66.3|80.3|
|sentence-transformers/distiluse-base-multilingual-cased-v1|SQuAD|12.1192053|19.90539262|24.5884579|31.85430464|
|sentence-transformers/distiluse-base-multilingual-cased-v1|BoolQ|9.785932722|17.21712538|20.48929664|25.56574924|
|sentence-transformers/distiluse-base-multilingual-cased-v2|pqa|63.65591398|78.92473118|84.62365591|90|
|sentence-transformers/distiluse-base-multilingual-cased-v2|PersianQuAD|70|85.5|89.1|94.9|
|sentence-transformers/distiluse-base-multilingual-cased-v2|SQuAD|36.00756859|53.38694418|60.90823084|70.12298959|
|sentence-transformers/distiluse-base-multilingual-cased-v2|BoolQ|32.59938838|51.74311927|59.05198777|68.25688073|
|sentence-transformers/LaBSE|pqa|80.53763441|91.1827957|93.87096774|96.23655914|
|sentence-transformers/LaBSE|PersianQuAD|79.3|90.8|94.1|96.3|
|sentence-transformers/LaBSE|SQuAD|39.3755913|56.93472091|64.44654683|74.15326395|
|sentence-transformers/LaBSE|BoolQ|34.4648318|50.82568807|57.21712538|65.99388379|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|pqa|40.32258065|58.17204301|65.2688172|76.34408602|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|PersianQuAD|47.6|67.2|75.6|88.8|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|SQuAD|12.00567644|22.63008515|29.04446547|39.01608325|
|m3hrdadfi/bert-zwnj-wnli-mean-tokens|BoolQ|11.98776758|20.48929664|24.83180428|31.43730887|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|pqa|56.77419355|76.4516129|84.51612903|91.50537634|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|PersianQuAD|58.8|81.1|89.6|94.5|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|SQuAD|18.8268685|32.98013245|40.08514664|50.80416272|
|m3hrdadfi/bert-fa-base-uncased-wikinli-mean-tokens|BoolQ|18.10397554|30.3058104|36.75840979|45.81039755|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|pqa|54.08602151|72.90322581|79.89247312|87.41935484|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|PersianQuAD|62.4|83.6|92|98|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|SQuAD|19.57426679|33.18826868|40.41627247|50.52980132|
|m3hrdadfi/bert-fa-base-uncased-wikitriplet-mean-tokens|BoolQ|18.44036697|29.75535168|35.41284404|42.93577982|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|pqa|11.72043011|22.15053763|29.03225806|43.44086022|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|PersianQuAD|25.8|50.1|59.6|74.1|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|SQuAD|1.617786187|4.228949858|6.291390728|10.04730369|
|m3hrdadfi/bert-fa-base-uncased-farstail-mean-tokens|BoolQ|1.590214067|3.516819572|4.525993884|7.49235474|

**Note:** The above table provides hit@k results using dot product on four datasets (PersianQA, PersianQuAD, SQuAD, BoolQ).


## Conclusion
This benchmark serves as a comprehensive evaluation of Persian embedding models for question-answering tasks. The results indicate that certain models, particularly those designed for multilingual and Persian-specific contexts, excel in retrieval-augmented tasks.

## License

