## Federated Human Data API Specification

A proposal for interfacing with CEGA as part submission workflow and data access/retrieval in the context of the Federated Human Data project Work Package 2, meant as a start for a discussion.

The Interface specification consists of two parts:
* Submission Interface - based on existing interfaces between LocalEGA and CentralEGA done via amqps protocol using RabbitMQ
* Data Access/Retrieval Interface - based on existing EGA Data API implemented. From the API we extract just the relevant parts.

The Repository also contains existing JSON Schema for the AMQPS communication.

More information on the services and overall LocalEGA and communication with CEGA see: https://wiki.eduuni.fi/display/CSCDMI/SDP+System+Overview

### Submission Interface

The submission interface specification is aimed to be protocol agnostic, meaning e.g. either amqp(s) or http(s) could be utilised

### Access/Retrieval Interface
The access interface specification is aimed to be used with HTTPS and HTSGET protocols.