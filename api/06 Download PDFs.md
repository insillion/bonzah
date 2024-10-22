This endpoint retrieves the PDF file for a specific policy by making an HTTP GET request to the specified URL. The request does not include a request body, as it is a simple GET request to download the PDF file. The response will contain the PDF file for the requested policy.

### Query Parameters
|Key|Value|
|---|---|
|data_id|{{cdw_pdf_id}} : Fetches and downloads the policy document if a CDW product has been opted<br><br>{{rcli_pdf_id}} : Fetches and downloads the policy document if a RCLI product has been opted<br><br>{{sli_pdf_id}} : Fetches and downloads the policy document if a SLI product has been opted<br><br>{{pai_pdf_id}} : Fetches and downloads the policy document if a PAI product has been opted|
|download|1|
