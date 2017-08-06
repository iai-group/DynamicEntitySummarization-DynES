# Dynamic Entity Summarization (DynES)

This repository contains resources developed within the following paper:

	F. Hasibi, K. Balog, and S.E. Bratsberg. “Dynamic Factual Summaries for Entity Cards”,
	In proceedings of 40th ACM SIGIR conference on Research and Development in Information Retrieval (SIGIR ’17),  2017.

You can check the [paper](http://hasibi.com/files/sigir2017-dynes.pdf) and [presentation]() for detailed information.

The repository is structured as follows:

- `data/`: Queries, qrels files, and fact ranking collection
- `runs/`: Run files reported in the paper (Tables 2 and 3)
- `cs-layouts/`: Layouts of the crowd sourcing experiments

## Data

The the fact ranking collection and its corresponding qrels files are available under `data` directory. This directory is organized as follows:

- `queries.txt`: 100 query-entity pairs selected from the [DBpedia-Entity](https://github.com/iai-group/DBpedia-Entity) collection. The procedure of selecting these pairs is described in the paper. 
- `fact_ranking_coll.tsv`: The fact ranking collection, consisting of queries, entities, entity facts (subjects and objects), and their labels with respect to importance, relevance, and utility.
- `qrels_*.txt`: TREC style qrels files for fact ranking. The first three columns of each file represent: query, entity, and fact ID for the corresponding query-entity pair according to `fact_ranking_coll.tsv`. The files suffixed with *uri_only* contain only facts with URI objects (used for the results of Table 2 of the paper).    

## Crowd sourcing layouts

We performed four different types of crowd sourcing experiments in our paper, which we share their layouts under the `cs-layouts/` directory:

- `fact_ranking-importance.png`: Used for building fact ranking collection. The workers were presented with a single fact for an entity, and were asked to rate the importance of the fact w.r.t. the entity.
- `fact_ranking-relevance.png`: Similar to the preveious experiment, but the workers were also provided with a query and asked to assess the relevance of the entity fact w.r.t. the query. 
- `user_preference-fact_ranking.png`: The user preference study for evaluating the generated summaries. The workers were presented with two
summaries and were asked to select the preferred summary, or
the tie option. In this experiment, we applied the same summary generation algorithm, but feed it with a ranked list of facts from different methods.
- `user_preference-summary_generation.png`: Similar to the previous experiment, but different summary generation algorithms were applied to the same ranked list of facts.

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

If you have any questions, feel free to contact Faegheh Hasibi at <faegheh.hasibi@ntnu.no>.
