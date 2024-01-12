# ReBIT AA Specifications Update (Version 2.X)

On August 9th, 2023, ReBIT published a major update to the AA specifications in the form of Version 2.0.0 of the catalog of APIs that FIPs, AAs, and FIUs have to implement.

ReBIT also published a document outlining the strategy for network participants to adopt Version 2.0.0. The key elements (and dates) as per this strategy are:

- **Deprecation Date:** January 7th, 2024, for all 1.1.X versions (the ecosystem is currently live on 1.1.2). This is the date when a “countdown” starts ticking for network participants to move towards adopting 2.0. The current 1.1.X API MUST continue to be supported by each entity until the “decommission” date.

- **Plan of Action:** From January 7th, 2024: FIPs, AAs, and FIUs, as API providers, must pass 4 additional fields in the headers of the existing 1.1.x response bodies. Likewise, as API clients, they have to be able to receive and process these additional fields.

- **Decommission Date:** May 12, 2024, for the current 1.1.2 / 1.1.3 versions. After this date, any entity yet to adopt 2.0 cannot exchange messages with other entities in the network.

- **Co-existence Period:** The co-existence of the current and new versions until the “decommission” date. Different parts of the network may potentially use either of the two API versions to communicate with each other between January 7th and May 12th without any disruption in the overall message flow.

## For a FIP/FIU

### For UAT Testing
Once the FIP/FIU has implemented the [Rebit 2.0 specs](https://api.rebit.org.in/), the FIP/FIU system must test its implementation in the UAT environment.

**As an API caller**
- Update the interface to the CR GET API in UAT to parse the baseurl attribute in the response as per the following format: `baseurl: "v1:<url for v1>, v2:<url for v2>"`. 
- Test your parsing logic using the following dummy AA entity in the UAT CR- Entity ID: AA00023400. 
- Fetch the entity details of the AA that you are planning to test your 2.X implementation with using their entity details as per this [sheet](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md).

**As an API provider**
- Update the existing entity in UAT to indicate the base URL of version 2.x implementation.
- Such changes can be made directly using the AA commons portal in the following format: `"v1:<url for v1>, v2:<url for v2>"`. In case a new FIU/FIP chooses to go live directly on V2 without supporting V1, the baseurl format should be: `baseurl: "v2:<url for v2>"` 
- Test with AAs that are ready in UAT on V2.0 using this [link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md).

After successful testing in the UAT environment, FIP/FIUs can indicate their readiness to go live on production.

## For Moving to Production
After successful testing in UAT, FIP/FIUs can now declare themselves ready for production. To declare themselves as live, FIP/FIUs must request an update to their existing Prod CR entry or request a new entry only in case they have not implemented V1.x.

- FIP/FIUs must first integrate the CR GET API V2.0 that returns both the V1 and V2 base URLs for entities that are live on V2. The same codebase tested in UAT as mentioned above in the steps under "As an API caller" will be used in this step. 
- Once the integration of the CR GET API V2.0 is complete, FIP/FIUs can request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).
- The GET API V2.0 will be in production starting Jan 25th, 2024. The same is already enabled in UAT.
  `Prod Endpoint:  `
  `UAT Endpoint:`
