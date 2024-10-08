This endpoint makes an HTTP GET request to retrieve information about a specific policy. The `policy_id` parameter in the query string should be provided to identify the policy.

### Request Body

This request does not require a request body.

### Response Body

The response will include the details of the policy identified by the `policy_id`, such as policy name, type, coverage details, and any additional information related to the policy.

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | Error message |
| `data` | Object | Contains the main data of the response. |
| `data.quote_id` | String | Unique identifier for the quote. Example: `Q000000001703`. |
| `data.quote_no` | String | Quote number. Example: `Q202401000403`. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.trip_start_date` | String (DateTime) | The start date and time of the trip. Format: `MM/DD/YYYY HH:MM:SS`. UTC Time |
| `data.trip_end_date` | String (DateTime) | The end date and time of the trip. Format: `MM/DD/YYYY HH:MM:SS`. UTC Time |
| `data.pickup_country` | String | Country of pickup. Example: `United States`. |
| `data.pickup_state` | String | State of pickup. Example: `New York`. |
| `data.residence_country` | String | The residence country of the user. Example: `United States`. |
| `data.drop_off_time` | String | Drop-off time. Example: `Same`. |
| `data.residence_state` | String | The residence state of the user. Example: `New York`. |
| `data.cdw_cover` | Boolean | Indicates if Collision Damage Waiver (CDW) coverage is opted. |
| `data.rcli_cover` | Boolean | Indicates if Renter's Contingent Liability Insurance (RCLI) coverage is opted. |
| `data.sli_cover` | Boolean | Indicates if Supplemental Liability Insurance (SLI) coverage is opted. |
| `data.pai_cover` | Boolean | Indicates if Personal Accident Insurance (PAI) coverage is opted. |
| `data.total_days` | Float | Total number of days covered. Example: `2.083333333333333`. |
| `data.cdw_rate` | String | Rate for CDW coverage. Example: `"$21.95 / 24 hours"`. |
| `data.rcli_rate` | String | Rate for RCLI coverage. Example: `"$14.88 / 24 hours"`. |
| `data.sli_rate` | String | Rate for SLI coverage. Example: `"$11.90 / 24 hours"`. |
| `data.pai_rate` | String | Rate for PAI coverage. Example: `"$6.90 / 24 hours"`. |
| `data.f_cov_lable_prem1` | String | Coverage label premium 1. Example: `"$25,000.00"`. |
| `data.f_cov_lable_prem2` | String | Coverage label premium 2. Example: `"$50,000.00"`. |
| `data.f_cov_lable_prem3` | String | Coverage label premium 3. Example: `"$10,000.00"`. |
| `data.coverage_information` | Array of Objects | List of optional coverages and their details. |
| `data.coverage_information[].optional_addon_cover_name` | String | Name of the optional addon cover. Example: `Collision Damage Waiver (CDW)`. |
| `data.coverage_information[].opted` | String | Indicates if the addon cover is opted. Example: `Yes`. |
| `data.coverage_information[].optional_addon_praram1` | Float | Primary parameter related to the addon cover. Example: `21.95`. |
| `data.coverage_information[].optional_addon_praram2` | String | Secondary parameter related to the addon cover. Example: `""`. |
| `data.coverage_information[].optional_addon_premium` | Float | Premium for the addon cover. Example: `23.78`. |
| `data.coverage_information[].added` | Boolean | Indicates if the addon is added. Example: `true`. |
| `data.coverage_information[].addon_cover_seq_no` | String | Sequence number for the addon cover. Example: `DATIGI20240924000263`. |
| `data.coverage_information[].policy_created_date` | String (Date) | Date when the policy was created. Format: `MM/DD/YYYY`. Example: `09/24/2024`. |
| `data.total_premium` | Float | Total premium calculated. Example: `60.26`. |
| `data.first_name` | String | The first name of the user. Example: `Loopit`. |
| `data.last_name` | String | The last name of the user. Example: `User`. |
| `data.dob` | String (Date) | Date of birth of the user. Format: `MM/DD/YYYY`. Example: `06/25/1975`. |
| `data.pri_email_address` | String | Primary email address of the user. Example: `loopituser@gmail.com`. |
| `data.alt_email_address` | String | Alternate email address of the user. Example: `testuser@gmail.com`. |
| `data.address_line_1` | String | First line of the address. Example: `address1`. |
| `data.address_line_2` | String | Second line of the address. Example: `address2`. |
| `data.zip_code` | String | Zip code of the address. Example: `01061`. |
| `data.phone_no` | String | Phone number of the user. Example: `13431233245`. |
| `data.state` | String | State of the address. Example: `Massachusetts`. |
| `data.city` | String | City of the address. Example: `Northampton`. |
| `data.select_country` | String | Selected country. Example: `United States`. |
| `data.select_state` | String | Selected state. Example: `New York`. |
| `data.country` | String | Country code. Example: `US`. |
| `data.source` | String | Source of the request. Example: `loopit`. |
| `data.broker_name` | String | Name of the broker. Example: `Loopit Group`. |
| `data.policy_no` | String | Policy number. Example: `BORD2024092401000009`. |
| `data.c_ts` | String (DateTime) | Timestamp when the record was created. Format: `MM/DD/YYYY HH:MM:SS`. UTC Time |
| `data.payment_id` | String | Unique identifier for the payment. Example: `PY000000001056`. |
| `data.paid_amount` | Float | Amount paid. Example: `60.26`. |
| `data.issue_date` | String (DateTime) | Date and time when the policy was issued. Format: `MM/DD/YYYY HH:MM:SS`. UTC Time |
| `data.cdw_pdf_id` | Integer | PDF ID for the CDW cover document. Example: `11264`. |
| `data.rcli_pdf_id` | Integer | PDF ID for the RCLI cover document. Example: `11266`. |
| `data.sli_pdf_id` | Integer | PDF ID for the SLI cover document. Example: `11267`. |
| `data.pai_pdf_id` | Integer | PDF ID for the PAI cover document. Example: `11265`. |