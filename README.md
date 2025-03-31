# D3.4: Association of cell assembly and testing data via a digital twin, and an implementation for integrating battery-cell history containing both automated and manual data

This deliverable demonstrates the integration of coin cell data and metadata collected from manual/automated assembly and testing experiments into an ELN, including timestamped metadata for recording sample history. The functionality is implemented in the [Aurora Cycler Manager](https://github.com/EmpaEconversion/aurora-cycler-manager/tree/0.5.1).

## Authors

- Nukorn Plainpan (Empa)
- Graham Kimbell (Empa)
- Corsin Battaglia (Empa)

## Short-term goal

The goal of this deliverable is to demonstrate the storing of data and metadata from coin cell assembly and testing experiments in an ELN in an automated fashion. The metadata includes timestamps for each process to provide a historical record of the sample.

## Achievement

We have developed an application for battery sample tracking and cycling data analysis, featuring a graphical user interface called [Aurora Cycler Manager](https://github.com/EmpaEconversion/aurora-cycler-manager/tree/0.5.1). As part of this deliverable, we have integrated the capability to automatically upload battery cycling data and metadata to the OpenBis Electronic Lab Notebook (ELN). The feature includes automatic semantic annotation of metadata using the BattINFO ontology, leveraging the tools developed in deliverable [D3.3](https://github.com/ord-premise/battery-domain-specific-language). The complete history of the cell—including both assembly and cycling—can be tracked using timestamps embedded in the raw data (stored in the HDF5 file). The Aurora Cycler Manager is in active development. The link provided here points to the version used in this work.

## Long-term goals

A more robust design is presently being fleshed-out and implemented following the design established in our previous [deliverable on digital twin interfaces](https://github.com/ord-premise/digital-twins-interface-design) in storing coin cell assembly and testing data and metadata in an ELN. The proposed ELN structure facilitates cell history via a hierarchical relationship of components, assemblies, cells, cycling processes, and datasets.

To further integrate cell provenance, we propose the concept of a sample state, a new object that is linked to the sample digital twin but is lighter, only representing information regarding the current state of the sample (e.g., charge, cycling metadata). The assembly process yields the sample digital twin. From there, each cycling protocol begins with a sample state as input (e.g., state 0: **assembled**) and yields as a product a new state object (e.g., state 1: **formed**, or state 2: **charged**, etc.). Subsequent cycling protocols MUST begin from the last available state object.

Through the concept of a sample state, objectively separated from the metadata-rich sample object, we can establish a historical relationship that tracks the journey of a sample (of a unique identifier) through the processes of assembly and cycling. We will demonstrate state changes across these two distinct processes, though in principle, and when desired/appropriate, the cycling process can be further broken down into sub-processes (e.g., SEI formation, long-term cycling, etc.).

This repository will evolve as we continue to work towards these goals.

## External links

- [openBIS](https://openbis.ch/)
- [Aurora cycler manager version 0.5.1](https://github.com/EmpaEconversion/aurora-cycler-manager/tree/0.5.1)

## Acknowledgements

The [PREMISE](https://ord-premise.org/) project is supported by the [Open Research Data Program](https://ethrat.ch/en/eth-domain/open-research-data/) of the ETH Board.

![image](https://ord-premise.org/assets/img/logos/PREMISE-logo.svg)

![image](https://ethrat.ch/wp-content/uploads/2021/12/ethr_en_rgb_black.svg)
