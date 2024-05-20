# API Documentation

## Ingestion Request

### 1. Get Ingestion Request by ID
Retrieve details of a specific ingestion request.

**Endpoint:** `GET /api/v1/ingestion_requests/17`

**Request:**
```sh
curl -X 'GET' \
  'http://localhost:3000/api/v1/ingestion_requests/17' \
  -H 'accept: */*'

Response: JSON object with details of the ingestion request.

