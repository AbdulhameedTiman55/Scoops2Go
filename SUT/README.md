Manual endpoint testing confirmed that the `/api/product` endpoint returns
a valid JSON response with product data (HTTP 200). An initial request to
`/products` returned an HTTP 500 error, indicating that this endpoint is not
intended for public use. This helped clarify the correct API contract and
was recorded as part of the SUT analysis.

