# ReBIT AA Specifications Update (Version 2.0.0)

On August 9th, 2023, ReBIT published a major update to the AA specifications in the form of Version 2.0.0 of the catalog of APIs that FIPs, AAs, and FIUs have to implement.

ReBIT also published a document outlining the strategy for network participants to adopt Version 2.0.0. The key elements (and dates) as per this strategy are:

- **Deprecation Date:** January 7th, 2024, for all 1.1.X versions (the ecosystem is currently live on 1.1.2). This is the date when a “countdown” starts ticking for network participants to move towards adopting 2.0. The current 1.1.X API MUST continue to be supported by each entity until the “decommission” date.

- **Plan of Action:** From January 7th, 2024: FIPs, AAs, and FIUs, as API providers, must pass 4 additional fields in the headers of the existing 1.1.x response bodies. Likewise, as API clients, they have to be able to receive and process these additional fields.

- **Decommission Date:** May 12, 2024, for the current 1.1.2 / 1.1.3 versions. After this date, any entity yet to adopt 2.0 cannot exchange messages with other entities in the network.

- **Co-existence Period:** The co-existence of the current and new versions until the “decommission” date. Different parts of the network may potentially use either of the two API versions to communicate with each other between January 7th and May 12th without any disruption in the overall message flow.

## For a AA

### For UAT Testing
Once the AA has implemented the [Rebit 2.0 specs](https://api.rebit.org.in/), the AA system must test its implementation in the UAT environment. 

**As an API caller**
- Develop the parsing logic to parse the response from the CR GET API in UAT as per the following format of baseurl-

  `baseurl:"v1:<url for v1>, v2:<url for v2>"`. 
- This step replicates the behavior of CR GET API V2.0 in production. This change will not impact the current CR GET API V1.0. More details on the changes in the CR and GET API can be found [here](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Changes_in_CR_and_APIs.md)
- Test your parsing logic using the following dummy FIP and FIU entities in the UAT CR using these Entity IDs: FIP89545, FIU00, FIU00020001, FIPGSP001-23.           

**As an API provider**
- Create a new entity in the UAT CR to indicate the base URL of version 2.x implementation. It is advised that the existing UAT Entity ID of the AA remains unchanged to ensure FIUs and FIPs currently testing with the AA in UAT on the existing v1.x version are not affected. The new entity ID should contain the baseurl's for both V1.1.2 and V2.X
- Such changes can be made directly using the AA Commons portal in the following format-

  `baseurl:"v1:<url for v1>, v2:<url for v2>"` 
- Request an update to the status on this [link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md) by writing to [kunal@sahamati.org.in](mailto:kunal@sahamati.org.in)

Once all steps are completed, an AA can begin testing with other entities in the UAT environment and get their implementation certified, details of certifiers can be found [here](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Status_of_Certifiers.md) After successful testing in the UAT environment, AAs can indicate their readiness to go live on production.

## For Moving to Production
After successful testing in UAT, AAs can now declare themselves ready for production. To declare themselves live, AAs must request an update to their existing Prod CR entry.

- AAs must first integrate the CR GET API V2.0 that returns the V1 and V2 base URLs for live entities on V2. The same codebase tested in UAT as mentioned above in the steps under "As an API caller" will be used in this step.
- Once the CR GET API V2.0 integration is complete, AAs can request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).
- The GET API V2.0 will be in production starting Jan 25th, 2024. The same is already enabled in UAT.
`Prod Endpoint: `
`UAT Endpoint`
