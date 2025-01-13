### Retrieve Pending Endorsement Details

This endpoint makes an HTTP GET request to retrieve pending endorsement details for a specific policy.

#### Request

- Method: `GET`
    
- URL: `{{host}}/api/v1/Bonzah/endorsement_pending`
    
- Query Parameters:
    
    - `policy_id` (string, required): The ID of the policy for which pending endorsement details are to be retrieved.
        

#### Response

The response for this request will be a JSON array

| **Field Name** | **Type** | **Description** |
| --- | --- | --- |

| `status` | Integer | The status of the response. Typically, `0` indicates success. |

| `txt` | String | An optional message or text response. |

| `data` | Array | An array containing endorsement details. |

| `data[ ].endorsement_id` | String | Unique identifier for the endorsement. Example: `EN000000000058`. |

| `data[ ].endorsement_name` | String | Name of the endorsement. Example: `Name change endorsement`. |

| `data[ ].prd_endorsement_id` | String | Unique identifier for the product endorsement. Example: `PE000000000002`. |

| `data[ ].policy_id` | String | Unique identifier for the policy. Example: `P000000001703`. |

| `data[ ].policy_no` | String | Policy number associated with the endorsement. Example: `BORD2024092401000009`. |

| `data[ ].endorsement_no` | String or Null | Endorsement number associated with the policy. Null if not available. |

| `data[ ].eproposal_id` | String | Unique identifier for the endorsement proposal. Example: `EP000000000058`. |

| `data[ ].assigned_to` | String | Email of the person assigned to this endorsement. Example: `loopituser@insillion.com`. |

| `data[ ].status` | String | Status of the endorsement. Example: `In Progress`. |

| `data[ ].assigned_on` | String (DateTime) | Date and time when the endorsement was assigned. Format: `MM/DD/YYYY HH:MM:SS`. Example: `09/24/2024 05:35:54`. |

| `data[ ].created_by` | String | Email of the user who created the endorsement. Example: `loopituser@insillion.com`. |
