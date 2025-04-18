# **GET** `/api/v1/Bonzah/master`

This `master` API endpoint allows the user to load master data based on the below requests.

### Request Body

- `master_name` (string, required): The name of the master to be created.
    
- `values` (string, required): The values associated with the master.
    
- `filter` (string, required): The filter criteria for the master.
    
- `filter_value` (string, required): The value for the filter criteria.
    

---

**Payload for Country Master:-**

{  
"master_name": "country",  
"values": "country",  
"filter": "",  
"filter_value": ""  
}

**Country Master Response:**

This will provide pickup country list

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | Error message |
| `data` | Object | An object containing the data related to the response. |
| `data.country` | Array | An array of country names included in the response. |
| `data.country[]` | String | A single country name from the array. Example: `United States`. |

---

**Payload for Zipcode master:-**

{  
"master_name": "zipcode",  
"values": "city,state,country",  
"filter": "zipcode",  
"filter_value": "01009"  
}

**Zipcode master Response:**

city,country & state will be fetched based on the given zipcode

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | Error message |
| `data` | Object | An object containing the location data related to the response. |
| `data.city` | String | The name of the city. Example: `Bondsville`. |
| `data.country` | String | The country code. Example: `US` for the United States. |
| `data.state` | String | The name of the state. Example: `Massachusetts`. |

---

**Payload for State Master**:-

{  
"master_name": "state",  
"values": "state",  
"filter": "country",  
"filter_value": "United States"  
}

**State Master Response:-**

This will provide pickup state based on the filtered country

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | An optional message or text response. |
| `data` | Array | An array containing a list of U.S. states and territories. Each element is a string representing the name of a state or territory. |
| `data[n]` | String | The name of a state or territory, where `n` is the index in the array. Example: `Alabama`, `Alaska`, `New York`, etc. |

---

**Payload for Residence Country Master**:-

{  
"master_name": "residence_country",  
"values": "country",  
"filter": "",  
"filter_value": ""  
}

**Residence Country Master Response:-**

This will provide residence country lilst

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |
| `status` | Integer | The status of the response. Typically, `0` indicates success. |
| `txt` | String | An optional message or text response. |
| `data` | Array | An array containing a list of countries. Each element is an object representing a country. |
| `data[n]` | Object | An object containing country information, where `n` is the index in the array. |
| `data[n].country` | String | The name of a country, where `n` is the index in the array. Examples include "Afghanistan", "Albania", etc. |

---

**Payload for Residence State Master:-**

{  
"master_name": "residence_state",  
"values": "state",  
"filter": "country",  
"filter_value": "United States"  
}

**Residence State Master Response:-**

This will provide residence state lists based on filtered country

| Field | Type | Description |
| --- | --- | --- |
| **status** | `integer` | Represents the status of the response. `0` indicates a successful request, while other values may indicate different statuses (e.g., errors). |
| **txt** | `string` | A message related to the status. This field may contain additional information or error messages; in this case, it is an empty string. |
| **data** | `array` | An array of objects, each representing a state or territory. Each object contains: |
| **data\[\].state** | `string` | The name of the state or territory (e.g., "Alabama", "California"). |