# D3.4: Association of cell assembly and testing data via a digital twin, and an implementation for integrating battery-cell history containing both automated and manual data

This deliverable demonstrates the integration of coin cell data and metadata collected from manual/automated assembly and testing experiments into an ELN, including timestamped metadata for recording sample history. The involved scripts are also provided.

## Authors

- Nukorn Plainpan (Empa)
- Corsin Battaglia (Empa)

## Short-term goal

The goal of this deliverable is to demonstrate the storing of data and metadata from coin cell assembly and testing experiments in an ELN in an automated fashion. The metadata includes timestamps for each process to provide a historical record of the sample.

## Achievement

We developed a script for deploying collected data and metadata from coin cell assembly and testing experiments by in-lab hardware/software into the openBIS ELN including history-tracking metadata (timestamps).

## Long-term goals

A more robust design is presently being fleshed-out and implemented following the design established in our previous [deliverable on digital twin interfaces](https://github.com/ord-premise/digital-twins-interface-design) in storing coin cell assembly and testing data and metadata in an ELN. The proposed ELN structure facilitates cell history via a hierarchical relationship of components, assemblies, cells, cycling processes, and datasets.

To further integrate cell provenance, we propose the concept of a sample state, a new object that is linked to the sample digital twin but is lighter, only representing information regarding the current state of the sample (e.g., charge, cycling metadata). The assembly process yields the sample digital twin. From there, each cycling protocol begins with a sample state as input (e.g., state 0: **assembled**) and yields as a product a new state object (e.g., state 1: **formed**, or state 2: **charged**, etc.). Subsequent cycling protocols MUST begin from the last available state object.

Through the concept of a sample state, objectively separated from the metadata-rich sample object, we can establish a historical relationship that tracks the journey of a sample (of a unique identifier) through the processes of assembly and cycling. We will demonstrate state changes across these two distinct processes, though in principle, and when desired/appropriate, the cycling process can be further broken down into sub-processes (e.g., SEI formation, long-term cycling, etc.).

This repository will evolve as we continue to work towards these goals.

## External links

- [openBIS](https://openbis.ch/)

## Acknowledgements

The [PREMISE](https://ord-premise.org/) project is supported by the [Open Research Data Program](https://ethrat.ch/en/eth-domain/open-research-data/) of the ETH Board.

![image](https://ord-premise.org/assets/img/logos/PREMISE-logo.svg)

![image](https://ethrat.ch/wp-content/uploads/2021/12/ethr_en_rgb_black.svg)
