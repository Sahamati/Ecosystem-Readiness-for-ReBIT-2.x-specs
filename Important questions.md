## What are the major changes that a FIU or FIP has to make to go live on Rebit 2.x specs?

To go live on Rebit 2.x specs, entities need to follow these steps:

1. **Implement the specs:** Implement the specifications as outlined on [api.rebit.org.in](api.rebit.org.in).
   
2. **Test the GET API of the Sahamati CR:** The Sahamati CR now hosts entity details in the following format: BaseUrl: `v1:<url for v1>, v2:<url for v2>`. FIUs and FIPs are expected to be able to parse the entity details in the recommended format. For more details about the implementation refer to [Changes in the CR and APIs](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Changes_in_CR_and_APIs). All FIUs and FIPs are requested to test their implementation of the GET API in the CR in UAT according to the new format. Use the following dummy AA to test your logic- Entity ID: AA00023400

3. **Test in the UAT environment:** Test the implementation in the UAT environment. To find AAs that are live in UAT on ReBiT 2.x, refer to [this link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Readiness_of_AAs.md).

4. **Get certified:** Get the FIP/FIU implementation certified. Check the status of certifiers' readiness at [this link](https://github.com/Sahamati/Ecosystem-Readiness-for-ReBIT-2.x-specs-/blob/main/Status_of_Certifiers.md).

## Do entities need to create a new entry in the CR for their version implementation of ReBit 2.x specs?

No, entities do not need to create a new entry in the CR to declare their readiness for ReBit 2.x specs. The CR can host the endpoint of ReBit 2.x specs implementation by updating the base URL in the following format: `v1:<url for v1>, v2:<url for v2>`.

## How do entities declare their readiness for ReBit 2.x specs?

Entities can declare their readiness for ReBit 2.x specs by following these steps:

1. **Create the updated JSON:** Send an updated JSON as per the prescribed format for the base URL.

2. **Submit the request:** Send the updated JSON to [services@sahamati.org.in](mailto:services@sahamati.org.in).

OR 

1. **Use CR Onboarding API:** Alternatively, entities can use the CR Onboarding API to update their FIP/FIU as per the agreed-upon format for the base URL.

[Instructions to use the CR API](api.rebit.org.in).

## What is the deadline for the implementation of ReBit 2.x specs?

[Insert information about the deadline here.]

## How long do entities need to host both ReBit 1.2 versions and 2.x versions?

[Insert information about hosting both versions here.]
