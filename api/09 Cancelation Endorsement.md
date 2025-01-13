### Add New Endorsement for Cancel Policy

This endpoint allows you to add a new endorsement for cancel a policy.

**Request Body**

- `endorsement_id` (string): The ID of the endorsement.
    
- `eproposal_id` (string): The ID of the eproposal.
    
- `policy_cancel_date` (string): The date on which the policy is to be cancelled. (MM/DD/YYYY HH:mm:ss) UTC time
    
- `policy_id` (string): The ID of the policy.
    
- `endorsement_remarks` (string): Remarks for the endorsement.
    
- `finalize` (integer): Indicates whether the endorsement is to be finalized (0 for false, 1 for true).
    

**Response**  
The response will contain the status of the request and any relevant data related to the new endorsement and cancelled policy.  
Once the endorsement is finalized, it will be triggered to the underwriter to proceed further.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| status | Integer | The status of the response. Typically, 0 indicates success. |
| txt | String | Error message if any |
| data | Object | Contains the main data of the response. |
| data.message | String | A message indicating the status or action taken. |
| data.endorsement_id | String | The unique identifier for the endorsement. |
| data.eproposal_id | String | The unique identifier for the e-proposal. |
| data.policy_id | String | The unique identifier for the policy. |
| data.endorsement_no | String/Null | The endorsement number, if available (otherwise null). It will generate when endorsement completed |
| data.policy_no | String | The policy number associated with the endorsement. |
| data.endorsement_start_date | String | The start date of the endorsement in "MM/DD/YYYY HH:MM" format. By default trip start date will be used |
| data.endorsement_name | String | The name of the endorsement, e.g., "Policy Cancellation". |
| data.nstp_id | String | The NSTP identifier associated with the case. |
| data.computed_premium_value | Float | The calculated premium value for the endorsement. |
| data.premium_value | Float | The premium amount for the endorsement, which may be negative. |
| data.endorsement_remarks | String | Any remarks or comments related to the endorsement. |
| `data.errors` | Array | If the errors array has values, it means the endorsement contains errors that must be cleared to finalize |