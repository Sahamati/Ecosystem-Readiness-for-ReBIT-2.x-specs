## For a FIP

### For UAT Testing
Once the FIP has implemented the [Rebit 2.0 specs](link), the FIP system must test their implementation in the UAT environment.

**As an API caller**
Develop the parsing logic to parse the response from the CR GET API in UAT as per the following format: `"v1:<url for v1>, v2:<url for v2>"`. This step replicates the behavior of CR GET API V2.0 in production. This change will not impact the current CR GET API V1.0.
Test your parsing logic using the following dummy AA entity in the UAT CR- Entity ID: AA00023400.
Fetch the entity details of the AA that you are planning to test with using their entity details as per [this sheet](link).

**As an API provider**
Update the existing entity in UAT to indicate the base URL of version 2.x implementation. Such changes can be made directly using the AA commons portal in the following format: `"v1:<url for v1>, v2:<url for v2>"`.
Identify AA that are live on 20 using [this link](link).

Once all steps are completed, an FIP can begin testing with other AAs in the UAT environment. After successful testing in the UAT environment, FIPs can indicate their readiness to go live on production.

## For Moving to Production
After successful testing in UAT, FIPs can now declare themselves ready for production. To declare themselves as live, FIPs must request an update to their existing Prod CR entry.

-FIPs must first integrate the CR GET API V2.0 that returns both the V1 and V2 base URLs for entities that are live on V2.
-Once the integration of the CR GET API V2.0 is complete, FIPs can request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).
