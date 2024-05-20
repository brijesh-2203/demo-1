API Documentation
Ingestion Request
1. Get Ingestion Request by ID
Retrieve details of a specific ingestion request.

Endpoint: GET /api/v1/ingestion_requests/17

Request:

sh
Copy code
curl -X 'GET' \
  'http://localhost:3000/api/v1/ingestion_requests/17' \
  -H 'accept: */*'
Response: JSON object with details of the ingestion request.

2. Update Ingestion Request by ID
Update details of a specific ingestion request.

Endpoint: PUT /api/v1/ingestion_requests/17?submit=false

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/17?submit=false' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "requesterName": "John Doe Updated",
  "requesterMudid": "JD12345",
  "requesterEmail": "john.doe@example.com",
  "datasetName": "Clinical Trial Data",
  ...
  "externalSourceSecretKeyName": "external-secret-key"
}'
Response: JSON object with updated details of the ingestion request.

3. Get Ingestion Requests with Filters
Retrieve a list of ingestion requests with specified filters.

Endpoint: GET /api/v1/ingestion_requests?my_approvals=false&my_submissions=true&status=All&page=1&per_page=20&order_by=MODIFIED_DATE&order_direction=DESC

Request:

sh
Copy code
curl -X 'GET' \
  'http://localhost:3000/api/v1/ingestion_requests?my_approvals=false&my_submissions=true&status=All&page=1&per_page=20&order_by=MODIFIED_DATE&order_direction=DESC' \
  -H 'accept: */*'
Response: JSON array of ingestion requests.

4. Create a New Ingestion Request
Submit a new ingestion request.

Endpoint: POST /api/v1/ingestion_requests?submit=false

Request:

sh
Copy code
curl -X 'POST' \
  'http://localhost:3000/api/v1/ingestion_requests?submit=false' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "requesterName": "John Doe",
  "requesterMudid": "JD12345",
  "requesterEmail": "john.doe@example.com",
  "datasetName": "Clinical Trial Data",
  ...
  "externalSourceSecretKeyName": "external-secret-key"
}'
Response: JSON object with details of the newly created ingestion request.

Ingestion Request Status
1. Submit Ingestion Request
Submit a specific ingestion request.

Endpoint: PUT /api/v1/ingestion_requests/16/submit

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/submit' \
  -H 'accept: */*'
Response: Status confirmation of the submission.

2. Reject Ingestion Request
Reject a specific ingestion request with comments.

Endpoint: PUT /api/v1/ingestion_requests/15/reject

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/15/reject' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "decisionComments": "decisionComments",
  "notifyThroughEmail": true,
  "rejectionReason": "rejectionReason",
  "existingDataLocationIdentified": "existingDataLocationIdentified"
}'
Response: Status confirmation of the rejection.

3. Mark Ingestion Request as In Progress
Mark a specific ingestion request as ingestion in progress.

Endpoint: PUT /api/v1/ingestion_requests/16/ingestion_in_progress

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/ingestion_in_progress' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "decisionComments": "decisionComments",
  "notifyThroughEmail": true
}'
Response: Status confirmation of the ingestion in progress.

4. Mark Ingestion Request as Failed
Mark a specific ingestion request as ingestion failure.

Endpoint: PUT /api/v1/ingestion_requests/16/ingestion_failure

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/ingestion_failure' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "decisionComments": "decisionComments",
  "notifyThroughEmail": true
}'
Response: Status confirmation of the ingestion failure.

5. Mark Ingestion Request as Complete
Mark a specific ingestion request as ingestion complete.

Endpoint: PUT /api/v1/ingestion_requests/16/ingestion_complete

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/ingestion_complete' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "decisionComments": "decisionComments",
  "notifyThroughEmail": true
}'
Response: Status confirmation of the ingestion completion.

6. Approve Ingestion Request
Approve a specific ingestion request.

Endpoint: PUT /api/v1/ingestion_requests/16/approve

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/approve' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "decisionComments": "decisionComments",
  "notifyThroughEmail": true
}'
Response: Status confirmation of the approval.

Ingestion Request Note
1. Update Ingestion Request Note by ID
Update a note on a specific ingestion request.

Endpoint: PUT /api/v1/ingestion_requests/16/notes/5

Request:

sh
Copy code
curl -X 'PUT' \
  'http://localhost:3000/api/v1/ingestion_requests/16/notes/5' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "notes": "updatedNotes"
}'
Response: Status confirmation of the note update.

2. Delete Ingestion Request Note by ID
Delete a note from a specific ingestion request.

Endpoint: DELETE /api/v1/ingestion_requests/16/notes/5

Request:

sh
Copy code
curl -X 'DELETE' \
  'http://localhost:3000/api/v1/ingestion_requests/16/notes/5' \
  -H 'accept: */*'
Response: Status confirmation of the note deletion.

3. Add a Note to Ingestion Request
Add a new note to a specific ingestion request.

Endpoint: POST /api/v1/ingestion_requests/16/notes

Request:

sh
Copy code
curl -X 'POST' \
  'http://localhost:3000/api/v1/ingestion_requests/16/notes' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "notes": "demoNotes"
}'
Response: Status confirmation of the note addition.

Application Reference
1. Get Application References
Retrieve a list of application references.

Endpoint: GET /api/v1/application_references

Request:

sh
Copy code
curl -X 'GET' \
  'http://localhost:3000/api/v1/application_references' \
  -H 'accept: */*'
Response: JSON array of application references.
