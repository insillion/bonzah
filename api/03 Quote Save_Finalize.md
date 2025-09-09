# **POST** `/api/v1/Bonzah/quote`

This `quote` API endpoint generates an insurance quote based on the data passed for the rental

This API endpoint can also be used to save a partially completed quote that can be completed at a later time (using the quote_id).

To finalize a quote (where no modifications can be made), the "finalize" tag should pass "1" as it's value.

\*Please note - Once the quote has been saved, finalized and issued - Policy modifications will not allow the change of the customer's email address.

### Request

- Method: POST
    
- Endpoint: `{{host}}/api/v1/Bonzah/quote`
    
- Headers:
    
    - Content-Type: application/json
        
    - in-auth-token : {{token}}
        

**Request Body**  
The request body should be in JSON format and include the following parameters:

| Key | Type | Description |  |
| --- | --- | --- | --- |
| quote_id | String | Unique identifier for the quote | Optional |
| trip_start_date | date | Start date of the trip (MM/DD/YYYY) | Required |
| trip_end_date | date | End date of the trip (MM/DD/YYYY) | Required |
| pickup_country | String | Country for car pickup. Should be as per master | Required |
| pickup_state | String | State for car pickup. Should be as per master | Required |
| drop_off_time | String | Time for car drop-off.  <br>  <br>Same - If the time of vehicle drop-off is the same as the time of vehicle pick-up.  <br>  <br>Later - If the time of vehicle drop-off is later than the time of pickup | Required |
| residence_country | String | Country of residence. Should be as per master | Required |
| residence_state | String | State of residence. Should be as per master | Optional |
| cdw_cover | Boolean | Whether Collision Damage Waiver is included | Required if Opted |
| rcli_cover | Boolean | Whether Rental Car Liability Insurance is included | Required if Opted |
| sli_cover | Boolean | Whether Supplemental Liability Insurance is included | Required if Opted |
| pai_cover | Boolean | Whether Personal Accident Insurance is included | Required if Opted |
| first_name | String | First name of the insured person | Required |
| last_name | String | Last name of the insured person | Required |
| dob | date | Date of birth of the insured person (MM/DD/YYYY) | Required |
| pri_email_address | String | Primary email address of the insured person.  <br>  <br>\*Emails with policy confirmation and Pre-Post trip inspection links are send to this email ID. To view policy COIs call the requests 6a,6b,6c,6d after policy issuance | Required |
| alt_email_address | String | Alternate email address of the insured person | Optional |
| address_line_1 | String | Address line 1 of the insured person | Required |
| address_line_2 | String | Address line 2 of the insured person | Optional |
| zip_code | String | Zip code of the insured person | Required |
| inspection_done | String | Specifies the receiver of the vehicle Inspection emails. if inspection is to be done by the customer "**Renter"** is to be passed.  <br>  <br>If the vehicle inspections are to be carried out by the Rental Agency pass "**Rental Agency".**  <br>  <br>This is Mandatory if the CDW cover is selected | Required for CDW |
| source | String | Source of the request (Ex: API) | Required |
| phone_no | String | Phone number of the insured person (must be 11 digits long, including the country code without the + symbol, followed by the mobile number). | Required |
| license_no | String | Driver's licence no of the insured person | Required |
| drivers_license_state | String | State that issued the driver's license of the insured person | Required |
| age_first_licensed | Integer | Age when the insured person was first licensed to drive | Required |
| year | Integer | The model year of the vehicle | Required |
| make | String | The manufacturer of the vehicle (e.g., Toyota, Ford) | Required |
| model | String | The specific model of the vehicle (e.g., Camry, Mustang) | Required |
| license_plate | String | The vehicle's license plate number. | Required |
| state_licensed_in | String | The state where the vehicle is licensed (e.g., CA, NY). | Required |
| vehicle_class | String | The vechicle's class | Required |
| additional_drivers\[\] | array | An array of objects, where each object represents an additional driver.  <br>\[ first_name, last_name, email, dob and phone_no \] | Optional |
| first_name | string | The additional driver's first name. | Required |
| last_name | string | The additional driver's last name. | Required |
| email | string | The additional driver's email address. | Required |
| dob | string | The additional driver's date of birth. Format: MM/DD/YYYY. | Required |
| phone_no | string | Must be 11 digits: country code (no +) + mobile number. | Required |
| finalize | Number | 0 - Draft quote  <br>1 - Finalize quote  <br>Once finalized the quote can not be modified | Required to Finalize and Issue policy |

### Response

The response will be in JSON format and will include quote_id and premium details. quote_id should be passed if you modify any details on second time hit other wise new quote will be created.

StartFragment

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
| `data.trip_start_date` | String (Date) | The start date of the trip. Format: `MM/DD/YYYY.` |
| `data.trip_end_date` | String (Date) | The end date of the trip. Format: `MM/DD/YYYY.` |
| `data.pickup_country` | String | Country of pickup. Example: `United States`. |
| `data.pickup_state` | String | State of pickup. Example: `California`. |
| `data.residence_country` | String | The residence country of the user. Example: `United States`. |
| `data.drop_off_time` | String | Drop-off time. Example: `Same`. |
| `data.residence_state` | String | The residence state of the user. Example: `California`. |
| `data.cdw_cover` | Boolean | Indicates if Collision Damage Waiver (CDW) coverage is opted. |
| `data.rcli_cover` | Boolean | Indicates if Renter's Contingent Liability Insurance (RCLI) coverage is opted. |
| `data.sli_cover` | Boolean | Indicates if Supplemental Liability Insurance (SLI) coverage is opted. |
| `data.pai_cover` | Boolean | Indicates if Personal Accident Insurance (PAI) coverage is opted. |
| `data.cdw_rate` | String | Rate for CDW coverage. Example: `"$21.95 / 24 hours"`. |
| `data.rcli_rate` | String | Rate for RCLI coverage. Example: `"$14.88 / 24 hours"`. |
| `data.sli_rate` | String | Rate for SLI coverage. Example: `"$11.90 / 24 hours"`. |
| `data.pai_rate` | String | Rate for PAI coverage. Example: `"$6.90 / 24 hours"`. |
| `data.f_cov_lable_prem1` | String | RCLI Coverage limit for Bodily Injury - Per Person : Example: `"$25,000.00"`. |
| `data.f_cov_lable_prem2` | String | RCLI Coverage limit for Bodily Injury - Aggregate : Example: `"$50,000.00"`. |
| `data.f_cov_lable_prem3` | String | RCLI Coverage limit for Property Damage : Example: `"$10,000.00"`. |
| `data.coverage_information` | Array of Objects | List of optional coverages and their details. |
| `data.coverage_information[].optional_addon_cover_name` | String | Name of the optional addon cover. Example: `Collision Damage Waiver (CDW)`. |
| `data.coverage_information[].opted` | String | Indicates if the addon cover is opted. Example: `Yes`. |
| `data.coverage_information[].optional_addon_praram1` | Float | Primary parameter related to the addon cover. Example: `21.95`. |
| `data.coverage_information[].optional_addon_premium` | Float | Premium for the addon cover. Example: `23.78`. |
| `data.coverage_information[].added` | Boolean | Indicates if the addon is added. Example: `true`. |
| `data.total_premium` | Float | Total premium calculated. Example: `60.26`. |
| `data.first_name` | String | The first name of the user. Example: `John`. |
| `data.last_name` | String | The last name of the user. Example: `Appleseed`. |
| `data.dob` | String (Date) | Date of birth of the user. Format: `MM/DD/YYYY`. Example: `06/25/1975`. |
| `data.pri_email_address` | String | Primary email address of the user. Example: `johnappleseed@gmail.com`. |
| `data.alt_email_address` | String | Alternate email address of the user. Example: `janeappleseed@gmail.com`. |
| `data.address_line_1` | String | First line of the address. Example: `address1`. |
| `data.address_line_2` | String | Second line of the address. Example: `address2`. |
| `data.zip_code` | String | Zip code of the address. Example: `01061`. |
| `data.phone_no` | String | Phone number of the user. Example: `13431233245`. |
| `data.state` | String | State of the address. Example: `Massachusetts`. |
| `data.city` | String | City of the address. Example: `Northampton`. |
| `data.select_country` | String | Selected country. Example: `United States`. |
| `data.select_state` | String | Selected state. Example: `California`. |
| `data.country` | String | Country code. Example: `US`. |
| `data.source` | String | Source of the request. Example: API. |
| `data.broker_name` | String | Name of the Rental |
| `data.licence_no` | String | Driver's license number of the insured person. Example: `D1234567`. |
| `data.drivers_license_state` | String | State that issued the driver's license of the insured person. Example: `CA`. |
| `data.age_first_licensed` | Integer | Age when the insured person was first licensed to drive. Example: `18`. |
| `data.year` | Integer | The model year of the vehicle. Example: `2022`. |
| `data.make` | String | The manufacturer of the vehicle. Example: `Toyota`. |
| `data.model` | String | The specific model of the vehicle. Example: `Mustang`. |
| `data.license_plate` | String | The vehicle's license plate number. Example: `ABC-1234`. |
| `data.state_licensed_in` | String | The state where the vehicle is licensed. Example: `CA`. |
| `data.vehicle_class` | String | The Vehicle Class. Example: `SUV` |
| `data.additional_drivers[].first_name` | String | Additional driver's first name.  <br>Example: `Mike` |
| `data.additional_drivers[].last_name` | String | Additional driver's last name.  <br>Example: `T` |
| `data.additional_drivers[].email` | String | Additional driver's email.  <br>Example: `miket@gmail.com` |
| `data.additional_drivers[].dob` | String | Additional driver's date of birth`(MM/DD/YYYY).`  <br>Example: `07/29/1990` |
| `data.additional_drivers[].phone_no` | String | Additional driver's phone number.  <br>Example : `13251233246` |
