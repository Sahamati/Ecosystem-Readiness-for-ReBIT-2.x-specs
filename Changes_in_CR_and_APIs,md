# ReBIT AA Specifications Update (Version 2.0.0)

On August 9th, 2023, ReBIT published a major update to the AA specifications, in the form of Version 2.0.0 of the catalogue of APIs that FIPs, AAs, and FIUs have to implement.

ReBIT also published a document outlining the strategy for network participants to adopt Version 2.0.0. The key elements (and dates) as per this strategy are:

- **Deprecation Date:** January 7th, 2024, for all 1.1.X versions (the ecosystem is currently live on 1.1.2). This is the date when a “countdown” starts ticking for network participants to move towards adopting 2.0. The current 1.1.X API MUST continue to be supported by each entity until the “decommission” date.

- **Plan of Action:** From January 7th, 2024: FIPs, AAs, and FIUs, as API providers, have to pass 4 additional fields in the headers of the existing 1.1.x response bodies. Likewise, as API clients, they have to be able to receive and process these additional fields.

- **Decommission Date:** May 12, 2024, for the current 1.1.2 / 1.1.3 versions. After this date, any entity yet to adopt 2.0 will be unable to exchange messages with other entities in the network.

- **Co-existence Period:** The co-existence of the current version and the new version until the “decommission” date. Different parts of the network may potentially use either of the two API versions to communicate with each other between January 7th and May 12th, without any disruption in the overall message flow.

The purpose of this document is to elaborate on how point c will be achieved, with a particular focus on changes required in the Registry that Sahamati manages for the AA network.

## Changes in Sahamati CR

In order to accommodate the changes in the ecosystem, Sahamati's ecosystem assets like CR, token service, etc. have to adapt. Key changes in the Sahamati CR are expected:

- Ecosystem participants (FIPs, FIUs, and AAs) are expected to host more than one version of ReBiT specs implementation, and the CR must be able to support the same.

- Entities would want to test out their implementation and hence should be able to create new UAT CR entries using the AA commons portal.

- CR GET API that is used to fetch entity details from the CR will have to adapt to share information about the two implementations.

There are two scenarios that make it possible for entities to host two different implementations:

1. Entities can host the two implementations, and when an API request is received at the API endpoint, the entities can parse the request body and based on the version in the request body, route the request to the relevant implementation.

2. Entities can also host separate endpoints for the implementation of both versions. In this scenario, entities are expected to make calls for V2.x on the V2 endpoint and for V1.x on the V1 endpoint.

The first scenario is handled by the CR, and nothing changes for any entity calling the API. For the second scenario, while there is no change to the structure of the CR, entities that choose the 2nd implementation will need to update their base URL for the implementation of 2.x specs in the following format:

```markdown
baseurl: "v1:<url for v1.x>, v2:<url for v2.x>"

