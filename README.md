# MoviesDatabase API Documentation

## API Overview
The MoviesDatabase API is a comprehensive RESTful API that provides access to a vast collection of movie data including titles, release information, cast details, and more. It offers powerful filtering, sorting, and pagination capabilities, making it ideal for building movie discovery applications.

## Version
The API is currently at version 1.

## Available Endpoints

### `/titles`
The main endpoint for fetching movie titles with support for filtering, sorting, and pagination.
- **Description**: Returns a list of movie titles
- **Parameters**: `year`, `genre`, `sort`, `limit`, `page`

### `/titles/{id}`
Fetches detailed information about a specific title.
- **Description**: Returns detailed information for a specific movie title
- **Parameters**: `id` (required)

### `/titles/random`
Returns random titles from the database.
- **Description**: Fetches random movie titles
- **Parameters**: `limit`

### `/genres`
Lists all available genres in the database.

### `/actors`
Provides information about actors and their filmography.

## Request and Response Format

### Request Format
Requests are made using standard HTTP methods (GET, POST) with query parameters for filtering. Authentication is required via API key in headers.

Example request to fetch movies from 2020:

### Authentication
All requests to the MoviesDatabase API require authentication via an API key. The key must be included in the request headers:

- Header Name: x-rapidapi-key

- Header Value: Your unique API key obtained from RapidAPI

- Host Header: x-rapidapi-host: moviesdatabase.p.rapidapi.com

API keys should be kept secure and never exposed in client-side code. Store them in environment variables or server-side configurations.

### Error Handling
The API returns standard HTTP status codes along with error messages in the response body.

### Common Error Responses:
- 400 Bad Request: Invalid parameters or malformed request

- 401 Unauthorized: Missing or invalid API key

- 403 Forbidden: Insufficient permissions or rate limit exceeded

- 404 Not Found: Resource not found

- 429 Too Many Requests: Rate limit exceeded

- 500 Internal Server Error: Server-side error

```json 
{
  "message": "Invalid API key",
  "status_code": 401
}
```

### Error Handling Best Practices:
- Always check response status codes

- Implement retry logic for rate limiting

- Use try-catch blocks for API calls

- Provide user-friendly error messages

- Log errors for debugging