# Dynamic Entity Summarization (DynES)

This repository provides resources developed within the following paper:

	F. Hasibi, K. Balog, and S.E. Bratsberg. “Dynamic Factual Summaries for Entity Cards”,
	In proceedings of 40th ACM SIGIR conference on Research and Development in Information Retrieval (SIGIR ’17),  2017.

**You can check the author version of the [article](http://hasibi.com/files/sigir2017-dynes.pdf) and the [presentation](https://www.slideshare.net/FaeghehHasibi/sigir2017dynes) for more information.**


### Abstract

	*Entity cards are being used frequently in modern web search engines to offer a concise overview of an entity directly on the results page. These cards are composed of various elements, one of them being the entity summary: a selection of facts describing the entity from an underlying knowledge base. These summaries, while presenting a synopsis of the entity, can also directly address users’ information needs. In this paper, we make the first effort towards generating and evaluating such factual summaries. We introduce and address the novel problem of dynamic entity summarization for entity cards, and break it down to two specific subtasks: fact ranking and summary generation. We perform an extensive evaluation of our method using crowdsourcing. Our results show the effectiveness of our fact ranking approach and validate that users prefer dynamic summaries over static ones.*

## Repository files 

The repository is structured as follows:

- `data/`: Queries, qrels files, and fact ranking collection
- `runs/`: Run files reported in the paper (Tables 2 and 3)
- `cs-layouts/`: Layouts of the crowdsourcing experiments

### Data

The the fact ranking collection and its corresponding qrels files are available under `data` directory. This directory is organized as follows:

- `queries.txt`: 100 query-entity pairs selected from the [DBpedia-Entity](https://github.com/iai-group/DBpedia-Entity) collection. The procedure of selecting these pairs is described in the paper.
- `fact_ranking_coll.tsv`: The fact ranking collection, consisting of queries, entities, entity facts (subjects and objects), and their labels with respect to importance, relevance, and utility.
- `qrels_*.txt`: TREC style qrels files for fact ranking. The first three columns of each file represent: query, entity, and fact ID for the corresponding query-entity pair according to `fact_ranking_coll.tsv`. The files suffixed with *uri_only* contain only facts with URI objects (used for the results reported in Table 2 of the paper).    

### Crowdsourcing layouts

We performed four different types of crowdsourcing experiments in our paper;  we share their layouts under the `cs-layouts/` directory:

- `fact_ranking-importance.png`: Used for building the fact ranking collection. Workers were presented with a single fact for an entity, and were asked to rate the importance of the fact w.r.t. the entity.
- `fact_ranking-relevance.png`: Similar to the previous experiment, but workers were also provided with a query and asked to assess the relevance of the entity fact w.r.t. the query.
- `user_preference-fact_ranking.png`: An user preference study for evaluating the generated summaries. Workers were presented with two
summaries and were asked to select the preferred summary, or
the tie option. In this experiment, we applied the same summary generation algorithm, but used different methods for ranking facts.
- `user_preference-summary_generation.png`: Similar to the previous experiment, but different summary generation algorithms were compared, all of which used the same fact ranking method.

## Citation

If you use the resources presented in this repository, please cite:

```
@inproceedings{Hasibi:2017:DFS,
 author =    {Hasibi, Faegheh and Balog, Krisztian and Bratsberg, Svein Erik},
 title =     {Dynamic Factual Summaries for Entity Cards},
 booktitle = {Proceedings of the 40th International ACM SIGIR Conference on Research and Development in Information Retrieval},
 series =    {SIGIR '17},
 year =      {2017},
 pages =     {773--782},
 doi =       {10.1145/3077136.3080810},
 publisher = {ACM}
}
```

## Contact

Should you have any questions, please contact Faegheh Hasibi at hasibi.44[AT]gmail.com (with [AT] replaced by @).
