# nuScenes_Knowledge_Graph
Ontologies and Knowledge Graphs of the ICCV 2023 workshop paper "nuScenes Knowledge Graph - A comprehensive semantic representation of traffic scenes for trajectory prediction"

## Content
 `KnowledgeGraphs` contains the
  - **nuScenes Knowledge Graph (nSKG)**, a knowledge graph for the [nuScenes dataset](https://www.nuscenes.org/nuscenes), that models all scene participants and road elements, as well as their semantic and spatial relationships
  - **nuScenes Trajectory Prediction Graph (nSTP)**, a heterogeneous graph of the nuScenes dataset for trajectory prediction in [PyTorch Geometric (PyG)](https://pytorch-geometric.readthedocs.io/en/latest/) format. It extends nSKG for example by transformation into agents' local coordinate systems, relevant agent extraction, semanric relationships between agents.

`Ontology` contains the ontologies for the traffic participants (agents) and the map that form the basis of the created knowledge graphs

![nuScenes ontology excerpt](Assets/nSKG.png)

## How to use
**nSKG** represents the KG created on the basis of the nuScenes ontologies nuScenes_agent_onto.ttl and nuScenes_map_onto.ttl and materializing the [nuScenes annotation dataset](https://www.nuscenes.org/nuscenes#data-annotation). It can be used for applications where relational information between entities are important. The ontologies are in [Turtle](https://www.w3.org/TR/turtle/) format and can be viewed by ontology editors such as [Protoge](https://protege.standord.edu/) 

**nSTP** represents the extended version of nSKG, where agents are represented in local coordinate systems to enforce shift- and rotation-invariance. It also includes semantic relationships between agents, e.g. whether agents are on neighboring lanes, the same lane or might intersect. This is done based on the semantic scene graph describe in [(Towards Traffic Scene Description: The Semantic Scene Graph)](https://arxiv.org/abs/2111.10196). The data is provided in PyTorch Geometric format and directly be used to train graph neural network for trajectory prediction.

<p align=center>
<img src="Assets/Map-and-agent-map3.png" width="300px">
</p>

## About
Special thanks to Motional for the permission to distribute this modified version of the nuScenes dataset.

## Citation
If you use this work please cite
```
@inproceedings{
title={nuScenes Knowledge Graph - A comprehensive semantic representation of traffic scenes for trajectory prediction},
author={Leon Mlodzian and Zhigang Sun and Hendrik Berkemeyer and Sebastian Monka and Zixu Wang and Stefan Dietze and Lavdim Halilaj and Juergen Luettin},
booktitle={International Conference on Computer Vision (ICCV), Workhsop on Scene Graphs and Graph Representation Learning (SG2RL)},
year={2023}
}
```
## License
Shield: [![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa], 
with additional term described by the nuScenes [Terms of use](https://www.nuscenes.org/terms-of-use), in particular the "Licenses" section.

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
