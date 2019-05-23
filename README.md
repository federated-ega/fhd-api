## Federated Human Data API Specification Draft

A proposal for interfacing with CEGA as part submission workflow and data access/retrieval in the context of the Federated Human Data project Work Package 2, meant as a start for a discussion.

The Interface specification consists of two parts:
* Submission Interface - based on existing interfaces between LocalEGA and CentralEGA done via `amqps` protocol using RabbitMQ
* Data Access/Retrieval Interface - based on existing EGA Data API implemented. From the API we extract just the relevant parts.

The Repository also contains existing JSON Schema for the AMQPS communication.

More information on the services and overall LocalEGA and communication with CEGA see: https://wiki.eduuni.fi/display/CSCDMI/SDP+System+Overview

### Submission Interface

The submission interface specification is aimed to be protocol agnostic, meaning e.g. either amqp(s) or http(s) could be utilised.

One important part of the submission phase is retrieving the stableID from CEGA.
Metadata should be retrievable with a stableID and to be decided if a LocaEGA instance can collect and post metadata to CEGA.

### Access/Retrieval Interface
The access interface specification is aimed to be used with HTTPS and HTSGET protocols.
Current Access API provides an endpoint for variant search, similar in scope with GA4GH beacon specification, although beacon API is designed to operate on the dataset level. If there is a need to align the APIs they might need to operate on the same level, or we might be able to connect them via the handover protocol.

We also need to identify how to retrieve file to dataset mapping.

Based on existing [DataEdge OpenAPI specificaiton](https://github.com/EGA-archive/ega-data-api/blob/master/mock-services/openapi/dataedge/dataedge.yaml)

### Other Resources

Other resources to consider for future interface development:
* https://ga4gh.github.io/data-repository-service-schemas/
* https://app.swaggerhub.com/apis-docs/ELIXIR-Finland/Permissions/1.2 - needs further refinement
    * some suggestions are published here: https://github.com/CSCfi/elixir-rems-proxy/blob/master/suggestions.md
* https://github.com/ga4gh-beacon/specification - implemented by CSC, there is also a ELIXIR standard implementation
* [GA4GH Researcher Access claims](https://docs.google.com/document/d/11Wg-uL75ypU5eNu2p_xh9gspmbGtmLzmdq5VfPHBirE/edit)

### Open Questions

* What endpoints require access control e.g. JWT Token? - the interfaces were designed to he protocol agnostic, but there might be endpoints that require access control.
