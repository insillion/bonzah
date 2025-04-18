# **POST** `/api/v1/Bonzah/epayment`

### Endorsement Payment

This `epayment` endpoint allows the user to make an HTTP POST request to process the payment of the endorsement.

#### Request Body

- `payment_id` (string,Required): The ID of the ePayment to be processed.
    
- `amount` (number,Required): The amount of the premium for the ePayment.
    

#### Response

Once payment is complete, the endorsement number is generated.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | An optional message or text response. |
| `data` | Object | Contains the main data of the response. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.eproposal_id` | String | Unique identifier for the endorsement proposal. Example: `EP000000000057`. |
| `data.endorsement_no` | String | Endorsement number associated with the policy. Example: `BORD2024092401000009/EN02`. |
| `data.policy_no` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |
| `data.endorsement_id` | String | Unique identifier for the endorsement. Example: `EN000000000057`. |
| `data.endorsement_start_date` | String (Date) | Start date of the endorsement. Format: `MM/DD/YYYY`. Example: 09/24/1994. |
| `data.endorsement_name` | String | Name of the endorsement. Example: `Date Change Endorsement`. |
| `data.epayment_id` | String | Unique identifier for the endorsement payment. Example: `PY000000001058`. |
| `data.nstp_id` | String | Unique identifier for the non-standard transaction proposal (NSTP). Example: `N000000000043`. |
| `data.email` | String | Email address of the policyholder. Example: `abc@gmail.com`. |
| `data.endorsement_remarks` | String | Remarks associated with the endorsement. Empty if not provided. |
| `data.policy_start_date` | String (Date) | Start date of the policy. Format: `MM/DD/YYYY`. Example: `09/24/2024`. |
| `data.policy_end_date` | String (Date) | End date of the policy. Format: `MM/DD/YYYY`. Example: `09/26/2024`. |
| `data.premium_value` | Float | The new premium value due to the endorsement. Example: `55.64`. |
| `data.dropoff_option` | String | Option selected for dropping off. Example: `Same`. |
| `data.address_line_1` | String | First line of the address. Example: `address1`. |
| `data.address_line_2` | String | Second line of the address. Example: `address2`. |
| `data.first_name` | String | First name of the policyholder. Example: `User`. |
| `data.last_name` | String | Last name of the policyholder. Example: `Same`. |
| `data.zip_code` | String | ZIP code of the policyholder's address. Example: `01061`. |
| `data.country` | String | Country code of the policyholder's address. Example: `US`. |
| `data.state` | String | State of the policyholder's address. Example: `Massachusetts`. |
| `data.city` | String | City of the policyholder's address. Example: `Northampton`. |
| `data.dob` | String (Date) | Date of birth of the policyholder. Format: `MM/DD/YYYY`. Example: `06/25/1975`. |
| `data.assigned_to` | String | Email of the person assigned to this endorsement. Example: `abc@gmail.com`. |