This endpoint allows you to create a new endorsement to change personal details

There is no approval process for this request. Confirmation of the changes made are sent to the customer via email.


**Request Body**

The request should include the following parameters in the raw request body:

- `endorsement_id` (string): The ID of the endorsement.
    
- `eproposal_id` (string): The ID of the e-proposal.
    
- `policy_id` (string): The ID of the policy.
    
- `first_name` (string): The first name of the policyholder.
    
- `last_name` (string): The last name of the policyholder.
    
- `address_line_1` (string): The first line of the address.
    
- `address_line_2` (string): The second line of the address.
    
- `zip_code` (string): The zip code of the address.
    
- `country` (string): The country of the address.
    
- `city` (string): The city of the address.
    
- `state` (string): The state of the address.
    
- `dob` (string): The date of birth of the policyholder.
    
- `email` (string): The email address of the policyholder.
    
- `phone_no` (string): The phone number of the policyholder.
    
- `finalize` (integer): A flag to indicate whether the endorsement should be finalized (0 for false, 1 for true). Once finalized the quote can not be modified
    

**Response:**

The response to this request will contain the relevant information confirming the addition of the endorsement. endorsement_no will be received once endorsement done

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | An optional message or text response. |
| `data` | Object | Contains the main data of the response. |
| `data.message` | String | The message indicating the endorsement status. Example: `Endorsement Proposal completed`. |
| `data.endorsement_id` | String | Unique identifier for the endorsement. Example: `EN000000000059`. |
| `data.eproposal_id` | String | Unique identifier for the endorsement proposal. Example: `EP000000000059`. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.endorsement_no` | String | Endorsement number associated with the policy. Example: `BORD2024092401000009/EN01`. |
| `data.policy_no` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |
| `data.endorsement_start_date` | String (Date) | Start date of the endorsement. Format:`MM/DD/YYYY`. By default, the trip start date will be used if it is in the future; otherwise, the current date will be used.  <br>Example: 09/24/1994. |
| `data.endorsement_name` | String | Name of the endorsement. Example: `Name change endorsement`. |
| `data.epayment_id` | String | Unique identifier for the endorsement payment. Empty if not applicable. |
| `data.nstp_id` | String | Unique identifier for the non-standard transaction proposal (NSTP). Empty if not applicable. |
| `data.computed_premium_value` | Float | The computed total premium value after endorsement. Example: `0`. |
| `data.premium_value` | Float | The new premium value due to the endorsement. Example: `0`. |
| `data.address_line_1` | String | First line of the address. Example: `tt`. |
| `data.address_line_2` | String | Second line of the address. Empty if not provided. |
| `data.first_name` | String | First name of the policyholder after the endorsement. Example: `Endorsed`. |
| `data.last_name` | String | Last name of the policyholder after the endorsement. Example: `Name`. |
| `data.email` | String | Email address of the policyholder. Example: `abc@gmail.com`. |
| `data.zip_code` | String | ZIP code of the policyholder's address. Example: `01061`. |
| `data.country` | String | Country code of the policyholder's address. Example: `US`. |
| `data.state` | String | State of the policyholder's address. Example: `Massachusetts`. |
| `data.city` | String | City of the policyholder's address. Example: `Northampton`. |
| `data.dob` | String (Date) | Date of birth of the policyholder. Format: `MM/DD/YYYY`. Example: `07/29/1995`. |
| `data.assigned_to` | String | Email of the person assigned to this endorsement. Example: `abc@gmail.com`. |
| `data.errors` | Array | If the errors array has values, it means the endorsement contains errors that must be cleared to finalize |