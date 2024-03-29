# The Notre-Dame Fire (NDF) Dataset 
## A new dataset of Fake News
The Notre-Dame Fire (NDF) Dataset includes news articles and tweets produced during the Notre-Dame fire of April 2019. The event had a worldwide resonance and was subject to the creation and spread of several fake news.

The dataset includes 568 texts (87 articles and 481 tweets) annotated as Fake or Real, according to the methodology proposed in the paper "In-context annotation of Topic-Oriented Datasets of Fake News: A Case study on the Notre-Dame Fire Event".

### Annotation procedure

The key assumption behind the labelling of the NDF dataset is that integrating contextual knowledge in a crowdsourcing experiment is useful to approximate expert human annotation. We call this approach _in-context annotation_.

We performed three rating tasks on the same data, with the aim of proving the added value of context. 
Tasks are distinguished by the information provided (or accessible) to the raters during the labelling phase. 

The labelling methods are defined as follows:

- **Out-of-Context (OOC) Annotation** Given an article/post _t_ related to the topic _s_, participants to a standard crowdsourcing experiment are asked to decide whether _t_ is real or fake, without any supporting additional information. 
- **In-Context (IC) Annotation**: Participants to a crowdsourcing experiment are asked to label a post or article as fake or real news. In this task, annotators are also given a manually selected list of _known false news_. The list contains fake news that have been officially debunked to ascertain their falsity. Given an article/post _t_ related to a topic (event or public figure) _s_, and a list _F<sub>s</sub>_ of known fake news about _s_, participants have to decide if _t_ is a fake news or not. 
- **Manually fact-checked (MFC) annotation**: Each piece of information has been manually fact-checked to assess its truthfulness. Both the _known fake news_ and additional sources on the web were considered, sometimes tracing back the news to its origin.

## The dataset

The NDF dataset includes all the annotation layers. Provided labels correspond to the various rating tasks, namely the manually-fact-checked (MFC), the in-context (IC) and out-of-context (OOC) ones.
The repository includes three files:

### Main file

The file [NDFDataset.tsv](NDFDataset.tsv) contains the three levels of annotation, one for each rating task. The final label for each item and task consists in the majority vote (for the OOC and IC task) or the fact-checked decision (for the MFC annotation).
	
	
	| id  | url | MFC  | IC   | OOC  | data-type |
	|-----|-----|------|------|------|-----------|
	| 012 | url | Fake | Fake | Fake | article   |
	| 013 | url | Fake | Fake | Real | tweet     |
	
	Table: Sample from the NDF dataset. 



### Non-aggregated data

Two additional files are provided, that summarize the non-aggregated rating details of each crowdsourcing task (OOC and IC). The text id links the files to the main dataset file (LINK). The names of the files are:

- [NDFDataset-OOCratings.tsv](NDFDataset-OOCratings.tsv): Non-aggregated ratings of the OOC task.
- [NDFDataset-ICratings.tsv](NDFDataset-ICratings.tsv): Non-aggregated ratings of the IC task.
	
Note that the non-aggregated ratings are the absolute number of raters that actually voted for the corresponding class during the annotation process. The non-aggregated ratings are provided as part of the dataset for further analyses on the fake news and their specific linguistic and contextual characteristics.
	
A sample of the files is reported below.

	| id  | fake rates | real rates |
	|-----|------------|------------|
	| 012 | 14         | 6          |
	| 013 | 7          | 13         |

	Table: Non-aggregated OOC task ratings provided with the NDF dataset

</br>

	| id  | fake rates | real rates |
	|-----|------------|------------|
	| 012 | 18         | 2          |
	| 013 | 14         | 6          |
	
	Table: Non-aggregated IC task ratings provided with the NDF dataset

## Fair Use Policy

Please, cite the following paper if you intend to use the NDF dataset for your own research:

	@article{PASSARO2022657,
	title = {In-context annotation of topic-oriented datasets of fake news: A case study on the notre-dame fire event},
	journal = {Information Sciences},
	volume = {615},
	pages = {657-677},
	year = {2022},
	issn = {0020-0255},
	doi = {https://doi.org/10.1016/j.ins.2022.07.128},
	url = {https://www.sciencedirect.com/science/article/pii/S0020025522008167},
	author = {Lucia C. Passaro and Alessandro Bondielli and Pietro Dell’Oglio and Alessandro Lenci and Francesco Marcelloni},
	keywords = {Fake news, Dataset collection and annotation, Machine learning},
	abstract = {The problem of fake news detection is becoming increasingly interesting for several research fields. Different approaches have been proposed, based on either the content of the news itself or the context and properties of its spread over time, specifically on social media. In the literature, it does not exist a widely accepted general-purpose dataset for fake news detection, due to the complexity of the task and the increasing ability to produce fake news appearing credible in particular moments. In this paper, we propose a methodology to collect and label news pertinent to specific topics and subjects. Our methodology focuses on collecting data from social media about real-world events which are known to trigger fake news. We propose a labelling method based on crowdsourcing that is fast, reliable, and able to approximate expert human annotation. The proposed method exploits both the content of the data (i.e., the texts) and contextual information about fake news for a particular real-world event. The methodology is applied to collect and annotate the Notre-Dame Fire Dataset and to annotate part of the PHEME dataset. Evaluation is performed with fake news classifiers based on Transformers and fine-tuning. Results show that context-based annotation outperforms traditional crowdsourcing out-of-context annotation.}
	}
