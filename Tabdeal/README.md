## Live Code Question

Write code that goes long (buy) when there are positive percentage changes and goes short (sell) when
there are negative percentage changes in a given time-series list of data.

## Task

We want to have a B2B charge sales software. In it, we have a number of sellers, each with a credit. This credit increases by submitting a credit increase request. This is done by saving a model in the seller's database that we have selected, increasing their credit by the specified amount.

Then, by calling a POST API, the seller should be able to charge a specific phone number by a certain amount, and the same amount will be deducted from their credit. Naturally, the sellers' credit should never become negative. The accounting system must be consistent, meaning that every operation that increases or decreases the user's credit must be recorded. When summing up these records, the final credit of the seller should match what we calculated. For example, if one million charges have been added to the account and 60 charges of 5000 Tomans each have been sold, the remaining credit in the account should be 700,000 Tomans.

Of course, records of each transaction must be appropriately recorded for both credit increases and sales. We expect the software to perform well and accurately under heavy parallel loads.

I will handle API testing in parallel. Project delivery phases:

Phase 1:
1. Architecture and definition of models.
2. Correct functioning of the credit increase model (charges only once without re-saving).
3. Proper creation of logs related to charge sales.
4. Avoidance of negative credit in charge sales.
5. Avoidance of negative credit in credit increase (decrease).
6. Minimum executed testing and correct accounting. At least 2 sellers, each with at least 2 credit increases and each with at least 10 charge sales at different amounts.
7. Code should have atomicity (credit increase and decrease operations within one transaction).

Phase 2:
1. Simple test cases should be written, including at least 2 sellers, 10 credit increases, and 1000 charge sales (in series), and finally, the credit of the sellers should be accurately measured.
2. Parallel testing.
3. Complete understanding of the distinction between process and thread.
4. Real parallel testing (code should fail if safety thread and condition race are not handled).
5. Implement safety thread and re-test.
6. Measure the time response related to the charge sales API and report it in the following two conditions:
   1. With low traffic (1 request per second).
   2. With high traffic (20 requests per second and above).

- The deliberate omission of the structure and architecture of the system is intended to evaluate the individual's ability to design appropriate models.
- After receiving the project, notify us within a maximum of 1 day of the delivery date for the first phase of the project.
- A half-hour meeting will be held on this day, during which you will demonstrate the following:
  - Postman with API functionality.
  - Admin panel.
  - Models.
  - Logic codes.
- After the delivery of the first phase, any necessary corrections will be announced, and a date for the delivery of the second phase will be specified, with the remaining procedures similar to the first phase.
