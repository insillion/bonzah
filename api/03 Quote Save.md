## Bonzah Quote API

This API endpoint allows you to create a quote for car rental insurance through Bonzah.

### Request

- Method: POST
    
- Endpoint: `{{host}}/api/v1/Bonzah/quote`
    
- Headers:
    
    - Content-Type: application/json
        
    - in-auth-token : {{token}}
        

**Request Body**  
The request body should be in JSON format and include the following parameters:

| Key | Type | Description |
| --- | --- | --- |
| quote_id | String | Unique identifier for the quote |
| trip_start_date | date | Start date of the trip (MM/DD/YYYY HH:mm:ss) UTC time |
| trip_end_date | date | End date of the trip (MM/DD/YYYY HH:mm:ss) UTC time |
| pickup_country | String | Country for car pickup. Should be as per master |
| pickup_state | String | State for car pickup. Should be as per master |
| drop_off_time | String | Time for car drop-off.  <br>  <br>Same - If the time of vehicle drop-off is the same as the time of vehicle pick-up.  <br>  <br>Later - If the time of vehicle drop-off is later than the time of pickup |
| residence_country | String | Country of residence. Should be as per master |
| residence_state | String | State of residence. Should be as per master |
| cdw_cover | Boolean | Whether Collision Damage Waiver is included |
| rcli_cover | Boolean | Whether Rental Car Liability Insurance is included |
| sli_cover | Boolean | Whether Supplemental Liability Insurance is included |
| pai_cover | Boolean | Whether Personal Accident Insurance is included |
| first_name | String | First name of the insured person |
| last_name | String | Last name of the insured person |
| dob | date | Date of birth of the insured person (MM/DD/YYYY) |
| pri_email_address | String | Primary email address of the insured person.  <br>  <br>\* Emails will not be triggered. To view policy COIs call the requests 6,7,8,9 after policy issuance |
| alt_email_address | String | Alternate email address of the insured person |
| address_line_1 | String | Address line 1 of the insured person |
| address_line_2 | String | Address line 2 of the insured person |
| licence_no | String | Driver's licence no of the insured person |
| zip_code | String | Zip code of the insured person |
| inspection_done | String | Indicates if inspection is done by. If it b2c pass Renter and if it is loopit or b2b pass Renter/Rental Agency. Mandatory if CDW cover selected |
| source | String | Source of the request (Ex: API) |
| phone_no | String | Phone number of the insured person (must be 11 digits long, including the country code without the + symbol, followed by the mobile number). |


### Response

The response will be in JSON format and will include quote_id and premium details. quote_id should be passed if you modify any details on second time hit other wise new quote will be created.



| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | error message |
| `data` | Object | Contains the main data of the response. |
| `data.quote_id` | String | Unique identifier for the quote. Example: `Q000000001703`. |
| `data.quote_no` | String | Quote number associated with the quote. It will be generated If quote is finalized without any error.  <br>Example: `Q202401000403`. |
| `data.policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |
| `data.payment_id` | String | Unique identifier for the payment. It will be generated if quote is finalized wihtout any error. Example: `PY000000001056`. |
| `data.total_amount` | Float | Total amount payable. Example: `60.26`. |
| `data.trip_start_date` | String (DateTime) | The start date and time of the trip. Format: `MM/DD/YYYY HH:MM:SS`. UTC time |
| `data.trip_end_date` | String (DateTime) | The end date and time of the trip. Format: `MM/DD/YYYY HH:MM:SS`. UTC time |
| `data.pickup_country` | String | Country of pickup. Example: `United States`. |
| `data.pickup_state` | String | State of pickup. Example: `New York`. |
| `data.residence_country` | String | The residence country of the user. Example: `United States`. |
| `data.drop_off_time` | String | Drop-off time. Example: `Same`. |
| `data.residence_state` | String | The residence state of the user. Example: `New York`. |
| `data.cdw_cover` | Boolean | Indicates if Collision Damage Waiver (CDW) coverage is opted. |
| `data.rcli_cover` | Boolean | Indicates if Renter's Contingent Liability Insurance (RCLI) coverage is opted. |
| `data.sli_cover` | Boolean | Indicates if Supplemental Liability Insurance (SLI) coverage is opted. |
| `data.pai_cover` | Boolean | Indicates if Personal Accident Insurance (PAI) coverage is opted. |
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
| `data.coverage_information[].optional_addon_premium` | Float | Premium for the addon cover. Example: `23.78`. |
| `data.coverage_information[].added` | Boolean | Indicates if the addon is added. Example: `true`. |
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