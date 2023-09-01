# Backend Developer Coding Test

---

## Background

Our system utilizes Node.js, Redis, Bull queue and PostgreSQL. In this particular test scenario, we're working with a `workspace_id` serving as a means of segregating data within our tables.

Now, we're aspiring to integrate our system with Xero API to fetch contacts. However, keep in mind the rate limit for Xero’s API, which is 60 requests per minute.

## Task Description

Your assignment is to:

1. Fetch contacts from the Xero API that are associated with a specific `workspace_id`.
2. Implement a rate limiting system to adhere to the Xero API's restriction of 60 requests per minute, using Redis and Bull queue.
3. Work with the `workspace_id` within your solution, respecting its significance in the data fetching and storage operations.

Here's a closer look at how to approach this:

### 1. Fetching Contacts

Your task is to fetch contacts related to a particular `workspace_id` from the Xero API, and make sure to comply with Xero’s rate limit, which counts 60 requests per minute.

Use the following endpoint to fetch contacts: `GET https://api.xero.com/api.xro/2.0/Contacts` 

### 2. Implement Rate Limiting

Considering the Xero API rate limit, integrate a rate limiting strategy using Bull and Redis. Your designed method should dictate:

- As soon as a request for contacts is made, the request should be moved to the Bull queue.
- The queue should be manipulated in a way where only 60 requests get processed per minute to comply with Xero's rate limit.

### 3. Incorporate `workspace_id`

To mimic a scenario with logical segregation, your solution should:

- Ensure that only the contacts relevant to the specified `workspace_id` are fetched.
- Safeguard that the fetched data is stored in PostgreSQL, properly associated with the corresponding `workspace_id`.

## Onjectives

1. **Understanding of RESTful APIs and Server-Client Interaction**: Assess the candidate's knowledge of designing, integrating, and interacting with RESTful APIs. Can they successfully integrate the Xero API into the existing service, and do they properly handle API rate limiting?
  
2. **Performance Optimization**: Evaluate the candidate's skills in optimizing performance in a high-traffic environment. Are they able to create a request queue and properly implement rate limiting to maximize throughput while avoiding overloading the Xero API?

3. **Error Handling and Reliability**: Check the candidate's ability to design reliable backend systems and their approach to handling errors, especially around third-party services. Are they considering potential issues that might occur when integrating with Xero's API?

4. **Data Modeling and Management**: Determine the candidate's understanding of database design and data management in a project that hypothetically involves logical data segregation based on `workspace_id`. Do they comprehend how to design the required database schema and handle database interactions?

5. **Documentation and Code Readability**: Assess the candidate's capability to write clean, efficient, and readable code. Do they provide an organized `README.md` explaining their design, decisions, and code? It's important to evaluate if the candidate is able to document the process and ensure future maintainability of the code.

## Expected Deliverables

- Code written to fetch contacts from Xero API.
- Code that enforces a rate limiting mechanism for these requests using Redis and Bull queue.
- Adequate database schema to store the data fetched, specifically distinguishing by `workspace_id`.
- Clear and comprehensive `README.md` explaining your approach and justification for your decisions.
- A fully functioning API capable of fetching and storing contacts from Xero for any supplied `workspace_id`.

This task realistically would take from 1-2 days. It would be of advantage to submit your answer in a GitHub repository. Wishing you the best of luck!

Before proceeding with fetching and storing contacts from Xero API, follow these instructions to sign up for a free trial with Xero:

1. Go to [Xero’s free trial page](https://www.xero.com/au/signup/).
2. Enter your contact details, create a password, and click "Get Started". 
3. You will receive a confirmation email to verify your account. Follow the instructions given to confirm your account.
4. Log in to your newly created account.
5. To access the Xero API, navigate to "Developers" in the footer.
6. Under "My Apps", click "New app" to create a new application.
7. Fill out the application details, and you should have access to your API keys which you would need for authentication.
8. Start your development!

Please follow Xero's API rate limit for the scope of your application.

## References

- Xero API documentation (https://developer.xero.com/documentation/api/accounting/contacts)
- Bull queue documentation (https://docs.bullmq.io/)


