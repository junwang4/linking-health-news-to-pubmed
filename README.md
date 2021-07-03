# Data used in "Linking Health News to Research Literature"

### Reuters data ###
- used for training "journal sentence classifier" and "journal name NER"

**reuters/journal_sentences_labeled.csv**
```
sentence,jo,label
"These diseases have rarely been studied in the context of PM 2.5 and hospitalizations, the study team writes in The BMJ.",The BMJ,1
The type of drink most responsible for cancer seems to be whatever type of alcohol women drink the most.,,0
```

**reuters/journal_NER.txt**
```
One O
limitation O
...
, O
the O
authors O
note O
in O
BJU B-JO
International I-JO
. O
```

### Cardiff data ###
- used for evaluating the performance of CrossRef and home-made literature search engines

**cardiff/corpus_news_enhanced.csv**
```
news_id,news_date,news_title,news_content,jo_freq,per_freq,org_freq
05-11-028_mirror,2011-10-15,SUPERBUG CURE HOPE,"TARGETING a toxin released by MRSA could help combat the lethal superbug, scientists say..... The study, which suggests the toxin could be attacked with drugs, was published in journal Plos Pathogens.","{""Plos Pathogens"": 1}","{""Ross Fitzgerald"": 1}","{""the Roslin Institute"": 1, ""the University of Edinburgh"": 1, ""the Health Protection Agency"": 1, ""Plos Pathogens"": 1}"
```
jo_freq (JSON format): obtained by running the above Reuter dataset-trained journal sentence classifier and NER model.

per_freq and org_freq: obtained by running the [Stanza](https://stanfordnlp.github.io/stanza/) NER function.


**cardiff/corpus_linking.csv** (pm_id is the PubMed ID or PMID of the reported research paper)
```
news_id,pm_id
05-11-028_mirror,22022262
05-11-028_scotsman,22022262
```

**cardiff/corpus_literature_basic.csv** (this file is for reference only)
```
pm_id,pm_date,pm_title,pm_doi,pm_authors,pm_affiliations,pm_journals
```
