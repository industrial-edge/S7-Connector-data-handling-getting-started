# S7 Connector Data Handling Getting Started

This repository contains the source files to build the Simatic S7 Connector Data Handling Getting Started example.

- [S7 Connector Data Handling Getting Started](#s7-connector-data-handling-getting-started)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [Further requirements](#further-requirements)
    - [TIA Project](#tia-project)
  - [Configuration steps](#configuration-steps)
  - [Usage](#usage)
  - [Implementation](#implementation)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [License and Legal Information](#license-and-legal-information)
  - [Disclaimer](#disclaimer)

## Description

### Overview

This application example describes the implementation and usage of the Common configurator and IIH essentials using the example of an asset model.

![Use Case](docs/graphics/DataFlow.PNG)

### General task

The application read and write some data of the PLC. The data is published via SIMATIC S7 Connector and Databus where the IIH essentials can retrive the data. First, the SIMATIC S7 Connector, Databus and Common configurator  must be configured. Afterwards it is possible to add the varaibles in asset, And in the storage data to see the asset variables, which obtain the PLC Data information. The data can be visualized with graphical structure.

## Requirements

###  Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industrial Edge Device on IEM
- Installed System Configurators for Databus and SIMATIC S7 Connector
- Installed System Apps Databus and SIMATIC S7 Connector
- Installed Apps common configurator
- Edge device is connected to PLC
- TIA portal project loaded on PLC (e.g. for Tank filling application)

### Used components

- Industrial Edge Management V1.13.10/Kubernetes
  - Databus V2.2.0-3
  - Databus Configurator V2.2.0-4
  - Flow Creator V1.15.0
  - IIH Essentials V1.8.1 
  - Common Connector Configurator V1.8.1-1
  - SIMATIC S7 Connector V1.8.1
- Industrial Edge Device V1.10.0-9
- TIA Portal V16
- S7-1511C
- Web browser (Mozilla or Chrome)

### Further requirements

- IE Device is onboarded to a IE Management
- Databus Configurator is deployed to the IE Management
- Databus is deployed to the IE Device
- Flow Creator is deployed to the IE Device

### TIA Project

The used TIA Portal project can be found in the [src](src) -file under the following name and is also used for several further application examples:

- [HowTos_Sinus_Wave.7z](src/HowTos_Sinus_Wave.7z)

## Configuration steps

You can find the further information about the following steps in the [docs](docs/Installation.md)
- Configure PLC Connection
- Configure Flow Creator

## Usage

Once the application is successfully deployed, the sinus wave can be deployed in the web UI of the Flow Creator. The sinus parameters such as frequency, amplitude or offset can be controlled in the web UI. The web UI can be accessed via the button in the upper right corner. With the submit button the set parameters from above will be written into the PLC. The sinus can be viewed in the chart below.

![InkedDashboardsettings_LI.jpg](docs/graphics/InkedDashboardsettings_LI.jpg)

![Dashboard.PNG](docs/graphics/Dashboard.PNG)

## Implementation
A detailed description of the implementation of the project can be found in the [implementation](docs/Implementation.md) file

## Documentation
 
- You can find further documentation and help in the following links
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://forum.mendix.com/link/space/industrial-edge)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  - [Industrial Edge GitHub page](https://github.com/industrial-edge)
  - [Industrial Edge documentation page](https://docs.eu1.edge.siemens.cloud/index.html)
  
## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you are interested in contributing via Pull Request, please check the [Contribution License Agreement](Siemens_CLA_1.1.pdf) and forward a signed copy to [industrialedge.industry@siemens.com](mailto:industrialedge.industry@siemens.com?subject=CLA%20Agreement%20Industrial-Edge).

## License and Legal Information

Please read the [Legal information](LICENSE.txt).

## Disclaimer

IMPORTANT - PLEASE READ CAREFULLY:

This documentation describes how you can download and set up containers which consist of or contain third-party software. By following this documentation you agree that using such third-party software is done at your own discretion and risk. No advice or information, whether oral or written, obtained by you from us or from this documentation shall create any warranty for the third-party software. Additionally, by following these descriptions or using the contents of this documentation, you agree that you are responsible for complying with all third party licenses applicable to such third-party software. All product names, logos, and brands are property of their respective owners. All third-party company, product and service names used in this documentation are for identification purposes only. Use of these names, logos, and brands does not imply endorsement.
