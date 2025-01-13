# Retrieve Bonzah Endorsement Details

This endpoint allows you to retrieve the details of a specific Bonzah endorsement by providing the endorsement ID as a query parameter.

## Request

### Request URL

- Method: GET
    
- URL: `{{host}}/api/v1/Bonzah/endorsement?endorsement_id={{endorsement_id}}`
    

### Request Query Parameters

- `endorsement_id` (string, required): The ID of the endorsement for which details are to be retrieved.
    

## Response

The response will be a JSON object containing the details of the Bonzah endorsement.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | Error meesage |
| `data` | Object | Contains the main data of the response. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.eproposal_id` | String | Unique identifier for the endorsement proposal. Example: `EP000000000057`. |
| `data.endorsement_no` | String | Endorsement number associated with the policy. Example: `BORD2024092401000009/EN02`. |
| `data.policy_no` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |
| `data.endorsement_id` | String | Unique identifier for the endorsement. Example: `EN000000000057`. |
| `data.email` | String | Primary email address of the policyholder. Example: `abc@gmail.com`. |
| `data.pri_email_address` | String | Primary email address of the policyholder. (Same as `email`). |
| `data.endorsement_start_date` | String (Date) | Start date of the endorsement. Format: `MM/DD/YYYY`. Example: 09/24/1994. |
| `data.endorsement_name` | String | Name of the endorsement. Example: `Date Change Endorsement`. |
| `data.epayment_id` | String | Unique identifier for the endorsement payment. Example: `PY000000001058`. |
| `data.nstp_id` | String | Unique identifier for the non-standard transaction proposal (NSTP). Example: `N000000000043`. |
| `data.endorsement_remarks` | String | Remarks associated with the endorsement. Empty if not provided. |
| `data.policy_start_date` | String (Date) | Start date and time of the policy. Format: MM/DD/YYYY HH:MM:SS. UTC Time Example: 09/24/2024 13:00:00. |
| `data.policy_end_date` | String (Date) | End date and time of the policy. Format: MM/DD/YYYY HH:MM:SS. UTC Time Example: 09/26/2024 15:00:00. |
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
