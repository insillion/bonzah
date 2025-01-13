### Remove Pending Endorsement Requests

This endpoint allows you to remove pending endorsement. The eproposal_id parameter in the query string should be provided to identify the endorsement.

**Response**  
The response will contain the status of the request, and the data object will be empty. A status of 0 indicates that the pending endorsement has been successfully deleted. If the status is not 0, it will indicate an error, with the error message provided in the txt field and a corresponding status code.