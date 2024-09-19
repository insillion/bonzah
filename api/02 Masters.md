# GET /api/v1/Bonzah/master

`master` endpoint allows user to load master data based on the below requests.

### Request Body

- `master_name` (string, required): The name of the master to be created   
- `values` (string, required): The values associated with the master    
- `filter` (string, required): The filter criteria for the master
- `filter_value` (string, required): The value for the filter criteria

### Payload for Country Master
<pre lang="json">
{  
"master_name": "country",  
"values": "country",  
"filter": "",  
"filter_value": ""  
}
</pre>
### Payload for State Master
<pre lang="json">
{  
"master_name": "state",  
"values": "state",  
"filter": "country",  
"filter_value": "United States"  
}
</pre>
### Payload for Residence Country Master
<pre lang="json">
{  
"master_name": "residence_country",  
"values": "country",  
"filter": "",  
"filter_value": ""  
}
</pre>
### Payload for Residence State Master
<pre lang="json">
{  
"master_name": "residence_country",  
"values": "state",  
"filter": "country",  
"filter_value": "United States"  
}
</pre>