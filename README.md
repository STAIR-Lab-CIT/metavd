![MetaVD Logo](https://metavd.stair.center/images/logo.svg)

# MetaVD

MetaVD is a *Meta Video Dataset* for enhancing human action recognition datasets.
It provides human-annotated relationship labels between action classes across human action recognition datasets.
MetaVD is proposed in the following paper:

**Yuya Yoshikawa, Yutaro Shigeto, and Akikazu Takeuchi. "MetaVD: A Meta Video Dataset for enhancing human action recognition datasets." Computer Vision and Image Understanding 212 (2021): 103276. [[link](https://www.sciencedirect.com/science/article/pii/S107731422100120X)]**

MetaVD integrates the following datasets:
- [UCF101](https://www.crcv.ucf.edu/data/UCF101.php)
- [HMDB51](https://serre-lab.clps.brown.edu/resource/hmdb-a-large-human-motion-database/)
- [ActivityNet](http://activity-net.org/)
- [STAIR Actions](https://actions.stair.center/)
- [Charades](https://prior.allenai.org/projects/charades)
- [Kinetics-700](https://deepmind.com/research/open-source/kinetics)

This repository does _NOT_ provide videos in the datasets. 
For information on how to download the videos, please refer to the website of each dataset.


## Data Format
### Relation label data
MetaVD relation labels are provided in `metavd_v*.csv`.
Each row represents an individual relation from an action class, called as _source action class_ to another action class, called as _target action class_.
The row is composed of the following information.
- from_dataset (_str_): Dataset name of _source_ action class. Any of `ucf101`, `hmdb51`, `activitynet`, `stair_actions`, `charades`, `kinetics700`.
- from_action_idx (_int_): Index of _source_ action class. 
- from_action_name (_str_): Name of _source_ action class.
- to_dataset (_str_): Dataset name of _target_ action class. Any of `ucf101`, `hmdb51`, `activitynet`, `stair_actions`, `charades`, `kinetics700`.
- to_action_idx (_int_): Index of _target_ action class. 
- to_action_name (_str_): Name of _target_ action class.
- relation (_str_): Relation type. Any of `equal`, `similar` and `is-a`.

Relation types `equal` and `similar` are undirected, while only `is-a` is directional.
Note that, a pair of action classes with any of `equal` and `similar` appears in the file only once.

### Action class list
We provide the list of action classes of each dataset in `[dataset_name]_classes.csv`.
The 'idx' column corresponds to 'from_action_idx' and 'to_action_idx', and the 'name' column corresponds to 'from_action_name' and 'to_action_name' in relation label data.

## Citation
```bibtex
@article{yoshikawa2021metavd,
  title = {MetaVD: A Meta Video Dataset for enhancing human action recognition datasets},
  journal = {Computer Vision and Image Understanding},
  volume = {212},
  pages = {103276},
  year = {2021},
  issn = {1077-3142},
  doi = {https://doi.org/10.1016/j.cviu.2021.103276},
  url = {https://www.sciencedirect.com/science/article/pii/S107731422100120X},
  author = {Yuya Yoshikawa and Yutaro Shigeto and Akikazu Takeuchi},
  keywords = {Human action recognition, Video datasets}
}
```

## License
MetaVD relation label data (`metavd_v1.csv`) and action class lists (`[dataset_name]_classes.csv`) are licensed under [Creative Commons Attribution 4.0 International license (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/legalcode).

## Acknowledgement
This dataset is based on results obtained from a project, JPNP20006, commissioned by the New Energy and Industrial Technology Development Organization (NEDO). 

## Release Notes
- 1/6/2022: MetaVD is available for download
