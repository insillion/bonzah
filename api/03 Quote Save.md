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
| trip_start_date | date | Start date of the trip (MM-DD-YY) |
| trip_end_date | date | End date of the trip (MM-DD-YY) |
| pickup_country | String | Country for car pickup |
| pickup_state | String | State for car pickup |
| drop_off_time | String | Time for car drop-off |
| residence_country | String | Country of residence |
| residence_state | String | State of residence |
| cdw_cover | Boolean | Whether Collision Damage Waiver is included |
| rcli_cover | Boolean | Whether Rental Car Liability Insurance is included |
| sli_cover | Boolean | Whether Supplemental Liability Insurance is included |
| pai_cover | Boolean | Whether Personal Accident Insurance is included |
| first_name | String | First name of the insured person |
| last_name | String | Last name of the insured person |
| dob | date | Date of birth of the insured person (MM-DD-YY) |
| pri_email_address | String | Primary email address of the insured person |
| alt_email_address | String | Alternate email address of the insured person |
| address_line_1 | String | Address line 1 of the insured person |
| address_line_2 | String | Address line 2 of the insured person |
| zip_code | String | Zip code of the insured person |
| inspection_done | String | Indicates if inspection is done by. If it b2c pass Renter and if it is loopit or b2b pass Renter/Rental Agency. Mandatory for if CDW cover select |
| source | String | Source of the request (loopit/b2c) |
| phone_no | String | Phone number of the insured person |

### Response

The response will be in JSON format and will include quote_id and premium details. quote_id should be passed if you modify any details on second time hit other wise new quote will be created