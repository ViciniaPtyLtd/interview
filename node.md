# Backend Developer Coding Test

**Project: Co-working Space Management System**

---

## Background

Our system utilizes Node.js, Express, Redis, Bull queue, PostgreSQL, and Hasura. In this particular test scenario, we're working with a `workspace_id` serving as a means of segregating data within our tables.

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

