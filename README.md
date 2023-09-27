# nuScenes_Knowledge_Graph
Implementation and Knowledge Graphs of the ICCV 2023 workshop paper "nuScenes Knowledge Graph - A comprehensive semantic representation of traffic scenes for trajectory prediction"

## Content
 `Knowledge_Graph_Generation`contains the code for generating the knowledge graphs (KG) nSKG and nSTP from scratch (only required if you like create a modified version of the KGs) 
- `Knowledge_Graphs` contains the
  - **nuScenes Knowledge Graph (nSKG)**, a knowledge graph for the nuScenes dataset, that models all scene participants and road elements, as well as their semantic and spatial relationships
  - **nuScenes Trajectory Prediction Graph (nSTP)**, a heterogeneous graph of the nuScenes dataset for trajectory prediction in PyTorch Geometric (PyG) format. It extends nSKG for example by transformation into agents' local coordinate systems, relevant agent extraction, semanric relationships between agents.
- `lanelet2_agent_agent`contains the code for creating the semantic relationships between the agents
- `Ontologies` contains the ontologieg for the traffic participants (agents) and the map that form the basis of the created knowledge graphs
- `Onto_utils` contains ontology related utilities  

## How to use
**nSKG** represents the KG created on the basis of the nuScenes ontologies nuScenes_agent_onto.ttl and nuScenes_map_onto.ttl and the nuScenes annotation dataset. It can be used for applications where relational information between entities are important. 

**nSTP** represents the extended version of nSKG, where agents are represented in local coordinate systems to enforce shift- and rotation-invariance. It also includes semantic relationships between agents, e.g. whether agents are on neighboring lanes, the same lane or might intersect. The data is provided in PyTorch Geometric format and directly be used to train graph neural network for trajectory prediction.

To create a modified version of the nSKG, e.g. based on a modified ontology, you can use the `Knowledge_Graph_Generation` code. Please use the following stept
- TBD

## About
This project was developed by ...

Special thanks to Motional for the permission to distribute this modified version of the nuScenes dataset.

## Citation
If you use this work please cite
```
@inproceedings{
sch{\"o}nfeld2021you,
title={nuScenes Knowledge Graph - A comprehensive semantic representation of traffic scenes for trajectory prediction},
author={Leon Mlodzian and Zhigang Sun and Hendrik Berkemeyer and Sebastian Monka and Zixu Wang and StefanDietze and Lavdim Halilaj and Juergen Luettin},
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
