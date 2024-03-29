# Senior Backend Engineer at Roya Negar

This assignment evaluates your skills in designing and implementing a robust backend system for tracking user video watch time at Roya Negar. The primary goal is to create a backend service capable of processing events generated by a separate service, which records the time a user spends watching a video. The service should provide insights into the total movie watch time, total user watch time, and the latest moment watched by each user.

## Requirements

1. **Event Source:**
   - A separate service generates real-time events containing the username, movie ID, and timestamp.
   - The backend must handle a high volume of events.

2. **Data Storage:**
   - Implement a data storage solution to persistently store events, choosing an appropriate database technology (e.g., relational, NoSQL).
   - Store necessary information, such as user ID, movie ID, and timestamp.

3. **Watch Time Calculation:**
   - Design a mechanism to calculate total watch time for a specific movie and user by aggregating timestamps.
   - Update total watch time for each user and movie with each new event.

4. **Latest Moment Watched:**
   - Track the latest moment watched by each user for a specific movie.
   - Update this information with each new event to reflect the most recent timestamp.

5. **API Endpoints:**
   - Implement API endpoints to retrieve total watch time for a specific movie, total watch time for a user across all movies, and the latest moment watched for a user in a particular movie.

6. **Scalability and Performance:**
   - Consider scalability and performance optimizations to handle a growing number of users and events without compromising response times.

7. **Documentation:**
   - Provide clear documentation on setting up and running the backend service.
   - Include API documentation for the implemented endpoints.

## How to Run the Event Generator

The event generator sends events to your localhost on port 8000. Run the following command to start the generator:

```
docker compose up
```

## Payload Example

```json
{
  "user": "username",
  "slug": "show_slug",
  "at": 4500
}
```

## Submission Guidelines

- Submit your code along with instructions for running and testing the backend.
- Include documentation explaining your design decisions, trade-offs, and potential improvements.

## Acceptance Criteria

1. **Event Handling:**
   - Successfully receive and process events from the external service.

2. **Data Storage:**
   - Persistently store events in the chosen database.

3. **Watch Time Calculation:**
   - Accurately calculate total watch time for a specific movie and user.
   - Properly handle concurrent events to prevent data inconsistencies.

4. **Latest Moment Watched:**
   - Accurately track the latest moment watched by each user for a specific movie.
   - Update the latest moment watched correctly with new events.

5. **API Endpoints:**
   - Implement API endpoints for retrieving total watch time for a specific movie, total watch time for a user across all movies, and the latest moment watched by a user for a specific movie.

6. **Scalability and Performance:**
   - Capable of handling a large number of concurrent events and users without significant performance degradation.
   - Implement performance optimizations for quick response times.

7. **Error Handling:**
   - Implement appropriate error handling for invalid events, database errors, or API request failures.
   - Provide meaningful error messages for debugging.

8. **Readability and Maintainability:**
   - Ensure the code is well-organized, follows best practices, and is easy to understand.

**Note:** Your submission will be evaluated based on how well it meets these acceptance criteria. Feel free to provide additional information or insights to enhance the evaluation of your work.