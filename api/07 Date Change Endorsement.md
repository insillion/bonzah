### Policy Date Change Modification request

This endpoint allows the creation of a new endorsement (modification) of a policy to change its start and end dates.

\*Please note - Postponing the start date is allowed, however bringing the start date forward is not supported at this time.

For scenarios where there is no change in the net policy duration - No aditional premium / refund is calculated, and the shift in dates is accepted without any approval.

When there is an extension in the number of days, the "10. Endorsement Payment" API request must be called to confirm the collection of the additional premium.

In the instance where a refund amount is calculated (Reduction in policy duration / Cancelation of policy). the modification/cancelation request is then sent to Bonzah for approval. Once approved, the refund value is reinstated in the Rental's credit limit.

The status of the endorsement once submitted for approval can be received via the "12. Endorsement Pending" API request.

For all scenarios, the customer will receive appropriate communication/confirmation via mail (pri_email_address)

**Request Body**

- endorsement_id (string, optional): The ID of the endorsement.
    
- eproposal_id (string, optional): The ID of the e-proposal.
    
- policy_id (string, Required): The ID of the policy.
    
- policy_start_date (string, Required): The start date of the policy. (MM/DD/YYYY HH:mm:ss) UTC time
    
- policy_end_date (string, Required): The end date of the policy. (MM/DD/YYYY HH:mm:ss) UTC time
    
- endorsement_remarks (string, optional): Any remarks related to the endorsement.
    
- endo_source (String , Required ) Source of the request (Ex: API)
    
- finalize (integer, Required): Indicates whether the endorsement is to be finalized. Once finalized the endorsement can not be modified. Tag value should pass "1". As of now "0" will not allow.
    

**Response**  
The response for this request will be in JSON format.

If the date is extended, a payment ID will be included in the response, and payment should be processed accordingly.

If the date is reduced, an endorsement will be triggered, and the underwriter will take further action.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | Error message |
| `data` | Object | Contains the main data of the response. |
| `data.message` | String | The message indicating the status for endorsement. Example: `Endorsement Proposal completed or Assigned to Underwriter` |
| `data.endorsement_id` | String | Unique identifier for the endorsement. Example: `EN000000000057`. |
| `data.eproposal_id` | String | Unique identifier for the endorsement proposal. Example: `EP000000000057`. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.endorsement_no` | String (nullable) | Endorsement number. If not yet generated, this will be `null`. |
| `data.policy_no` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |
| `data.endorsement_start_date` | String (Date) | Start date of the endorsement. Format: `MM/DD/YYYY`. By default, the trip start date will be used if it is in the future; otherwise, the current date will be used.. Example: 09/24/1994. |
| `data.endorsement_name` | String | Name of the endorsement. Example: `Date Change Endorsement`. |
| `data.epayment_id` | String | Unique identifier for the endorsement payment. Example: `PY000000001058`. |
| `data.nstp_id` | String | Unique identifier for the non-standard transaction proposal (NSTP). Example: `N000000000043`. |
| `data.policy_start_date` | String (DateTime) | Start date and time of the policy. Format: `MM/DD/YYYY HH:MM:SS`. Example: `09/24/2024 13:00:00`. |
| `data.policy_end_date` | String (DateTime) | End date and time of the policy. Format: `MM/DD/YYYY HH:MM:SS`. Example: `09/26/2024 15:00:00`. |
| `data.computed_premium_value` | Float | The computed total premium value after endorsement. Example: `115.90`. |
| `data.premium_value` | Float | The new premium value due to the endorsement. Example: `55.64`. |
| `data.dropoff_option` | String | Drop-off option associated with the policy. Example: `Same`. |
| `data.premium_paid` | Float | The total premium amount paid before the endorsement. Example: `60.26`. |
| `data.endorsement_remarks` | String | Remarks or notes related to the endorsement. Example: `Endo remarks`. |
| `data.errors` | Array | If the errors array has values, it means the endorsement contains errors that must be cleared to finalize |