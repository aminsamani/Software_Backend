### Design and Implementation of a URL Shortener Service
#### (URL shorteners are commonly requested by many other companies, such as AVAN and SMARTECH.)
### ~ 2 days

### Introduction
In this project, This service, in addition to shortening URLs, should store information about users who have used our shortened URLs and use that data for analytics.
It is important to note that only users who are logged into their accounts should be able to create shortened URLs and view their analytics. Furthermore, all users should be able to be redirected to the original URL using our shortened URL.

The provided service should be ready to serve a large number of users, allowing the addition of 100,000 URLs and the redirection of users to the destination URL 100 million times in a day.

Example
```
 INPUT: https://example.com/my-very-long-URL-asdasdas
OUTPUT: https://myURLshortener.example.com/r/short-URL
```

Project Explanation

1. Registration and Login
    Every new user can create an account in our service using a username and password. This user should have the ability to log into the service using any preferred authentication method. The user can create an account with just an email, username, and password, and should be able to log in either with a username and password or with an email and password.
    Note: Due to security considerations, your views or APIs must have appropriate authentication and permission settings.

2. Creating Shortened URLs
A logged-in user can use the service to shorten their long URLs. In this method, the user, in addition to their original URL, can provide a string as a suggestion to the service. In this case, the service should use that string or a similar one as the path. If two different users submit the same original URL to the URL shortening service, they should receive different output.
Note: The term "path" refers to the URL-short part in the example above.


Transfer:

Users who visit the redirection pages of the service should be directly redirected to the original URL. It should be noted that the service needs to be prepared for a high number of these requests, so it is recommended to use the Redis database in this section.

Analytics:

In this section, information related to each of the shortened URLs should be provided to the user who created them. This data needs to be returned to the user quickly, so it should be handled asynchronously, and short intervals of user interactions should be created. This information includes the following sections, which should be provided for today, so far, and for the recent day, week, and month:

- Total views for each URL
  - Overall
  - Mobile vs. Desktop
  - Different browsers

- Number of unique users who have requested each URL
  -  Overall
  -  Mobile vs. Desktop
  - Different browsers

Note: Reporting should be possible in the following four time intervals:

1. From 00:00 of the current day until the current moment (for example, if it is currently 18:00 on a Tuesday, information for the past 18 hours from 00:00 to 18:00 on Tuesday should be provided).
2. The previous day (for example, if it is currently 18:00 on a Tuesday, information for the 24 hours of Monday from 00:00 to 23:59 should be provided).
3. The past seven days (for example, if it is currently 18:00 on a Tuesday, information for the seven-day period from the previous Wednesday to the current Tuesday should be provided).
4. The past thirty days (for example, if it is currently the 10th of the month, information for the thirty-day period from the 10th of the previous month to the 9th of the current month should be provided, assuming all months have thirty days).

Benchmark:

At this stage, the service's performance should be evaluated using a benchmarking tool over a one-minute interval. The output should include the number of transfers, the number of created URLs, and the number of analytics requests per second. The expectation is that the service should handle an average of 120 requests per second. The ratio of created URLs, transfers, and analytics requests should be 5%, 85%, and 10%, respectively.

Provide a brief report on the changes you have made to the system and the level of performance improvement achieved due to these changes.