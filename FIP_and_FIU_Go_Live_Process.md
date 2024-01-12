## For a FIP/FIU

### For UAT Testing
Once the FIP/FIU has implemented the [Rebit 2.0 specs](https://api.rebit.org.in/), the FIP/FIU system must test its implementation in the UAT environment.

**As an API caller**
- Develop the parsing logic to parse the response from the CR GET API in UAT as per the following format: `"v1:<url for v1>, v2:<url for v2>"`. 
- Test your parsing logic using the following dummy AA entity in the UAT CR- Entity ID: AA00023400.
- Fetch the entity details of the AA that you are planning to test with using their entity details as per this [sheet](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md).

**As an API provider**
- Update the existing entity in UAT to indicate the base URL of version 2.x implementation.
- Such changes can be made directly using the AA commons portal in the following format: `"v1:<url for v1>, v2:<url for v2>"`. In case a new FIU/FIP is choosing not go live on V1,they must also send the baseurl in the same format with a null in the v1 tag. 
- Identify AA that are live on V2.0 using this [link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md).

Once all steps are completed, an FIP/FIU can begin testing with other AAs in the UAT environment. After successful testing in the UAT environment, FIP/FIUs can indicate their readiness to go live on production.

## For Moving to Production
After successful testing in UAT, FIP/FIUs can now declare themselves ready for production. To declare themselves as live, FIP/FIUs must request an update to their existing Prod CR entry.

- FIP/FIUs must first integrate the CR GET API V2.0 that returns both the V1 and V2 base URLs for entities that are live on V2. The same codebase tested in UAT as mentioned above in the steps under "As an API caller" will be used in this step. 
- Once the integration of the CR GET API V2.0 is complete, FIP/FIUs can request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).
