
# Changes in Sahamati CR

To accommodate the changes in the ecosystem, Sahamati's ecosystem assets, like CR, token service, etc., have to adapt. Key changes in the Sahamati CR are expected:

- **Versioning Guidelines:** Entities (FIPs, FIUs, and AAs) are expected to host more than one version of ReBiT specs implementation. As per the ReBiT guidelines, the baseurl for implementing V2.X must contain the component '/V2' at the end of the URL. The agreed format for hosting multiple baseurls is  `v1:<url for v1>, v2:<url for v2>`.
  
- **Testing Implementation:** Entities can create new UAT CR entries using the AA Commons portal for testing. They can do so by referring to the following documents for [AAs](api.rebit.org.in) and [FIPs and FIUs](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/FIP_and_FIU_Go_Live_Process.md)

- **CR GET API Update:** The CR GET API will be updated to support information about the two implementations. A new version - V2 of the CR GET API in production will return comma-separated baseurls as per the prescribed format above. The current version in Production will continue only to return the v1 baseurls irrespective of if the entity has gone live on ReBiT 2.X implementation or not. This is to ensure smooth transition for entities during the phase where they can be live on either V1, or V2 or both.
- The GET API V2.0 will be in production starting Jan 25th, 2024.
  [Postman Collection](https://drive.google.com/drive/folders/1NmtiaL-Dv5fsEzGR79iWXr5Tlt__U6YZ?usp=sharing)
  `Prod Endpoint:  https://cr.sahamati.org.in/v2/entityInfo/<entitytype>`
  `UAT Endpoint: https://uatcr.sahamati.org.in/v2/entityInfo/<entitytype>`
