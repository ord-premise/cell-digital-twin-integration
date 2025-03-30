# D3.4: Association of cell assembly and testing data via a digital twin, and an implementation for integrating battery-cell history containing both automated and manual data

This deliverable demonstrates the integration of coin cell data and metadata collected from manual/automated assembly and testing experiments into an ELN following a hierarchical design that guarantees history traceability.

## Authors

- Nukorn Plainpan (Empa)
- Edan Bainglass (PSI)
- Fabio Lopes (Empa)
- Corsin Battaglia (Empa)

## Goal

The goal of this delieverable is to showcase an implementation of the design established in our previous [deliverable on digital twin interfaces](https://github.com/ord-premise/digital-twins-interface-design) in storing coin cell assembly and testing data and metadata in an ELN. The ELN structure facilitates cell history via a hierarchical relationship of components, assemblies, cells, cycling processes, and datasets.

To further integrate cell provenance, we introduce the concept of a sample state, a new object that is linked to the sample digital twin but is lighter, only representing information regarding the current state of the sample (e.g., charge, cycling metadata). The assembly process yields the sample digital twin. From there, each cycling protocol begins with a sample state as input (e.g., state 0: **assembled**) and yields as a product a new state object (e.g., state 1: **formed**, or state 2: **charged**, etc.). Subsequent cycling protocols MUST begin from the last available state object.

Through the concept of a sample state, objectively separated from the metadata-rich sample object, we can establish a historical relationship that tracks the journey of a sample (of a unique identifier) through the processes of assembly and cycling. Here we demonstrate state changes across these two distinct processes, though in principle, and when desired/appropriate, the cycling process can be further broken down into sub-processes (e.g., SEI formation, long-term cycling, etc.).

## Achievement

In this deliverable, we integrated coin cell data and metadata into an ELN in standard formats and hierarchical structure developed in PREMISE, providing a built-in base history tracking functionality via parent-child object relationships.

![Coin cell data integration in ELN](./figures/ELN_structure.png "Coin cell data integration in ELN")

![Assembly and cycling object relationships](./figures/object_relationship.png "Assembly and cycling object relationships")

We further demonstrated sample history tracking via manipulation and exchange of sample state objects across the ELN and experiment workflow manager.

![Provenance tracking through sample states](./figures/sample_state.png "Provenance tracking through sample states")

We showcase an example workflow capturing data and metadata from both manual and automated processes, further highlighting the applicability of the design in modeling a digital twin.

![Manual/automated metadata capture](./figures/manual_auto_workflow.png "Manual/automated metadata capture")

We also provide a demonstration on our website's tutorials page (link).

This deliverable is a collaboration between:

- PSI - digital twin modeling, history-tracking design conceptualization
- Empa nanotech@surfaces lab - openBIS expertese
- Empa Materials for Energy Conversion lab - coin cell assembly/testing, integration implementation

## External links

- [openBIS](https://openbis.ch/)

## Acknowledgements

The [PREMISE](https://ord-premise.org/) project is supported by the [Open Research Data Program](https://ethrat.ch/en/eth-domain/open-research-data/) of the ETH Board.

![image](https://ord-premise.org/assets/img/logos/PREMISE-logo.svg)

![image](https://ethrat.ch/wp-content/uploads/2021/12/ethr_en_rgb_black.svg)
