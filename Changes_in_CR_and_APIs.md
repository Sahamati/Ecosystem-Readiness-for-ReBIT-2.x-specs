# ReBIT AA Specifications Update (Version 2.0.0)

On August 9th, 2023, ReBIT published a major update to the AA specifications in the form of Version 2.0.0 of the catalog of APIs that FIPs, AAs, and FIUs have to implement.

ReBIT also published a document outlining the strategy for network participants to adopt Version 2.0.0. The key elements (and dates) as per this strategy are:

- **Deprecation Date:** January 7th, 2024, for all 1.1.X versions (the ecosystem is currently live on 1.1.2). This is the date when a “countdown” starts ticking for network participants to move towards adopting 2.0. The current 1.1.X API MUST continue to be supported by each entity until the “decommission” date.

- **Plan of Action:** From January 7th, 2024: FIPs, AAs, and FIUs, as API providers, must pass 4 additional fields in the headers of the existing 1.1.x response bodies. Likewise, as API clients, they have to be able to receive and process these additional fields.

- **Decommission Date:** May 12, 2024, for the current 1.1.2 / 1.1.3 versions. After this date, any entity yet to adopt 2.0 cannot exchange messages with other entities in the network.

- **Co-existence Period:** The co-existence of the current and new versions until the “decommission” date. Different parts of the network may potentially use either of the two API versions to communicate with each other between January 7th and May 12th without any disruption in the overall message flow.

## Changes in Sahamati CR

To accommodate the changes in the ecosystem, Sahamati's ecosystem assets, like CR, token service, etc., have to adapt. Key changes in the Sahamati CR are expected:

- **Versioning Guidelines:** Entities (FIPs, FIUs, and AAs) are expected to host more than one version of ReBiT specs implementation. As per the ReBiT guidelines, the baseurl for implementing V2.X must contain the component '/V2' at the end of the URL. The agreed format for hosting multiple baseurls is  `v1:<url for v1>, v2:<url for v2>`.
  
- **Testing Implementation:** Entities can create new UAT CR entries using the AA Commons portal for testing. They can do so by referring to the following documents for [AAs](api.rebit.org.in) and [FIPs and FIUs](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/FIP_and_FIU_Go_Live_Process.md)

- **CR GET API Update:** The CR GET API will be updated to support information about the two implementations. A new version - V2 of the CR GET API in production will return comma-separated baseurls as per the prescribed format above. The current version in Production will continue only to return the v1 baseurls irrespective of if the entity has gone live on ReBiT 2.X implementation or not. This is to ensure smooth transition for entities during the phase where they can be live on either V1, or V2 or both. 
