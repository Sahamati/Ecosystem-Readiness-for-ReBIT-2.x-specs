## For a AA

### For UAT Testing
Once the AA has implemented the [Rebit 2.0 specs](https://api.rebit.org.in/), the AA system must test its implementation in the UAT environment. 

**As an API caller**
- Develop the parsing logic to parse the response from the CR GET API in UAT as per the following format of baseurl-

  `baseurl:"v1:<url for v1>, v2:<url for v2>"`. 
- This step replicates the behavior of CR GET API V2.0 in production. This change will not impact the current CR GET API V1.0. More details on the changes in the CR and GET API can be found [here](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Changes_in_CR_and_APIs.md)
- Test your parsing logic using the following dummy FIP and FIU entity in the UAT CR using these Entity IDs: FIP89545, FIU00, FIU00020001, FIPGSP001-23.           

**As an API provider**
- Create a new entity in the UAT CR to indicate the base URL of version 2.x implementation.
- Such changes can be made directly using the AA commons portal in the following format-

  `baseurl:"v1:<url for v1>, v2:<url for v2>"` 
- Request an update to the update status on this [link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md) by writing to [kunal@sahamati.org.in](mailto:kunal@sahamati.org.in)

Once all steps are completed, an AA can begin testing with other entites in the UAT environment. After successful testing in the UAT environment, AAs can indicate their readiness to go live on production.

## For Moving to Production
After successful testing in UAT, AAs can now declare themselves ready for production. To declare themselves live, AAs must request an update to their existing Prod CR entry.

- AAs must first integrate the CR GET API V2.0 that returns the V1 and V2 base URLs for live entities on V2.
- Once the CR GET API V2.0 integration is complete, AAs can request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).
