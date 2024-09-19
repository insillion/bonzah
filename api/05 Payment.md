This endpoint allows the client to make a cash payment by sending a POST request to the specified URL. The request should include a JSON payload with the "key" parameter containing the payment ID and the "amount" parameter containing the total amount to be paid.

payment_id and amount to be passed which is recived from quote finalize API.

### Request Body
<pre lang="json">
{
    "key": "{{payment_id}}",
    "amount": {{total_amount}}
}
</pre>

Response will includes policy_no and policy_id. Once payment done policy will be generated