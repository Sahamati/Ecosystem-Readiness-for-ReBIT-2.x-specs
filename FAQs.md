# ReBIT AA Specifications Update (Version 2.X) - FAQs

## General FAQs

### Q1: What is the significance of the ReBIT AA Specifications Version 2.0.0 update?

A1: ReBIT published a major update to the AA specifications in the form of Version 2.0.0, affecting the catalog of APIs that FIPs, AAs, and FIUs implement. This update comes with a deprecation plan for older versions and introduces changes to response body headers.

### Q2: What are the key dates associated with the Version 2.0.0 update?

A2: The key dates include the Deprecation Date (Jan 7, 2024), Plan of Action starting from Jan 7, 2024, Decommission Date (May 12, 2024), and a Co-existence Period until the Decommission Date.

## For FIP/FIU

### Q3: How can a FIP/FIU perform UAT testing for the ReBIT 2.0 specs?

A3: After implementing the [Rebit 2.0 specs](https://api.rebit.org.in/), FIP/FIU should test in the UAT environment. For API callers, update the CR GET API interface to parse the baseurl attribute. For API providers, update the entity in UAT to indicate the base URL of version 2.x implementation. For more details on how to update, refer to [this sheet](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs/blob/main/Changes_in_CR_and_APIs.md)

### Q4: What steps should API callers take during UAT testing?

A4: API callers should update the interface with Sahamati to parse the baseurl attribute in the CR GET API response. Test parsing logic using a dummy AA entity (AA00023400) and fetch entity details from [this sheet](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs/blob/main/Readiness_of_AAs.md) to begin testing with AAs. 

### Q5: How can API providers indicate readiness for production after UAT testing?

A5: API providers should update the existing entity in UAT to indicate the base URL of the version 2.x implementation. Test with AAs ready in UAT on V2.0 using [this link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md). After successful testing, indicate readiness for production.

### Q6: How can FIP/FIUs move to production after UAT testing?

A6: After UAT testing, FIP/FIUs must integrate the CR GET API V2.0, which returns both V1 and V2 base URLs. API is expected to go live on 25th Jan 2024, for more details, refer to this [document](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs/blob/main/Changes_in_CR_and_APIs.md). Once complete, request entry into the CR by sending the updated prod JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in). 

### Q7: Where can details of certifiers for production implementation be found?

A7: Details of certifiers for certification of 2.x implementation can be found [here](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Status_of_Certifiers.md). Entities are recommended to get their implementation certified before moving to production. 

### Q8: What are the endpoints for the CR GET API V2.0 in production and UAT environments?

A8:
- Prod Endpoint: `<Specify Prod Endpoint>`
- UAT Endpoint: `<Specify UAT Endpoint>`
