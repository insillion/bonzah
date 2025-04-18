# **GET** `/api/v1/Bonzah/endorsement_completed`

This endpoint sends an HTTP GET request to retrieve information about completed endorsements for a specific policy. The `policy_id` query parameter should be included in the request URL to specify the policy for which the endorsement information is required.

### Request Body

This endpoint does not require a request body.

### Response Body

The response will include the details of the completed endorsements for the specified policy, such as endorsement ID, endorsement No, and any additional relevant information.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | An optional message or text response. |
| `data` | Array | An array containing endorsement details. |
| `data[ ].endorsementId` | String | Unique identifier for the endorsement. Example: `EN000000000057`. |
| `data[ ].policyId` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data[ ].policyNo` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |
| `data[ ].endorsementNo` | String | Endorsement number associated with the policy. Example: `BORD2024092401000009/EN02`. |
| `data[ ].insuredName` | String | Name of the insured person. Example: `Loopit User`. |
| `data[ ].endorsementName` | String | Name of the endorsement. Example: `Date Change Endorsement`. |
| `data[ ].insuredPhone` | String | Phone number of the insured person. Example: `13431233245`. |
| `data[ ].insuredEmail` | String | Email address of the insured person. Example: `loopituser@gmail.com`. |
| `data[ ].premium` | String | The premium associated with the endorsement. If no premium, it is an empty string. Example: `55.64`. |
| `data[ ].endorsedBy` | String | Email of the person who endorsed the policy. Example: `loopituser@insillion.com`. |
| `data[ ].created` | String (DateTime) | Date and time when the endorsement was created. Format: `MM/DD/YYYY HH:MM:SS`. Example: `09/24/2024 05:36:42`. |
| `data[ ].certId` | String or Null | Certificate ID associated with the endorsement. Empty string if not available. |
| `data[ ].effectiveDate` | String (Date) | Date when the endorsement becomes effective. Format: `MM/DD/YYYY`. Example: `09/24/2024`. |
| `data[ ].endorsementType` | String | Type of endorsement, either `Premium bearing` or `Non-Premium bearing`. Example: `Premium bearing`. |