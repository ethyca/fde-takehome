# Ethyca Technical Challenge -- Forward Deployed Privacy Engineer (FDPE)

## Overview
Welcome to the FDPE Technical Challenge!

This is a takehome technical challenge that should take between 2 - 3 hours at most. This isn't a programming interview - it's designed to help us understand how you navigate an unknown technical product and use your troubleshooting skills to find issues and make recommendations. Once you've finished this challenge, you'll submit a short write-up to us and then we'll walkthrough your solution on an interview call to go through the details together.

As part of this challenge, you'll start to get more familiar with Fides as a product and our documentation. Here are some initial links for reference which might come in handy:
- [Ethyca Docs Site](https://ethyca.com/docs)
- [Fides API Developer Docs](https://ethyca.com/docs/dev-docs/api)
- [FidesJS Developer Docs](https://ethyca.com/docs/dev-docs/js)
- [Fides Language Docs](https://ethyca.github.io/fideslang/)

## Fides Cloud Login

For this challenge, you'll be accessing the production Fides Cloud instance of an imaginary customer, the "Cookie House". We'll email you a link with your login & password so you can access this and follow along!

To get started, login to Fides Cloud here: https://fides-ethyca-interview.us.fides.ethyca.com/

## Setting the Scene

You're an Ethyca Forward Deployed Privacy Engineer who has been helping a customer integrate Fides into their own web app. This customer is the "Cookie House", a small online retailer of high-quality cookies - the edible kind, like "Choco Chip", not the ones that track your browser across the Internet!

Right now, this customer has been focused on configuring their "Data Inventory" - the list of systems they use to process user data. Their goal is to ensure all their key infrastructure is added to Fides so that they can run privacy reports for their compliance team.

Last week, you walked them through the following:
- Setting up their account in Fides Cloud
- Using the Fides Admin UI to manually populate their inventory: https://fides-ethyca-interview.us.fides.ethyca.com/datamap
- Showing them the (live) Fides OpenAPI page for their instance: https://fides-ethyca-interview.us.fides.ethyca.com/docs

During the call, their Engineering team asked if it was possible to use the Fides API programmatically create & update Systems in the inventory from their internal applications, and you pointed them to the Fides API Developer Docs to get started.

## Help Needed!

A few days later, you receive the following email:
> Hi there!
> 
> We've been using the Fides API the last few days and have run into an issue when trying to create a System for our analytics database...
>
> We got a Bearer token by calling the `POST /api/v1/login` API, and then used that to call `GET /api/v1/system`, which worked to give us a list of all the systems so far.
>
> However, when we tried to create a new system with `POST /api/v1/system` we ran into an error we couldn't quite figure out. We were trying to add our Analytics database as a system to the inventory and show that it receives data from our main Postgres database... can you help?
>
> Here's the JSON body we provided:
> ```
> {
>   "fides_key": "cookie_house_analytics_database",
>   "organization_fides_key": "default_organization",
>   "name": "Cookie House Analytics Database",
>   "description": "Analytics database for Cookie House metrics.",
>   "system_type": "Database",
>   "egress": "null",
>   "ingress": [
>     {
>       "fides_key": "postgres",
>       "type": "system",
>       "data_categories": ["user/contact/email"]
>     }
>   ],
>   "privacy_declarations": [],
>   "administrating_department": "Engineering"
> }
> ```
>
> The error message says something like "value is not a valid list", but we didn't take it much farther than that. What are we doing wrong here?
>
> Also, once we are able to create that system, can you explain how we'd edit it to make changes, like adding additional ingress/egress flows?
>
> Cheers,
>
> Jane Doe (Cooke House Engineering)

## Your Challenge

Help the customer! You can use any of your preferred tools, languages, editors, or frameworks to assist here, but please achieve the following:
1. Connect to the Fides API using the shared credentials and any tool you prefer
2. Try to reproduce the customer's issue and figure out their problem
3. Write a customer email response to help explain the problem and your solution
4. As needed, write up any imaginary tickets (bug/feature/docs) for the Ethyca team to explain any issues you find or suggestions to make the API or documentation easier to understand next time!


## Notes
- Please work independently without code review by others.
- It's our intention that you spend between 2 and 3 hours on this task.
- This challenge is deliberately vague on detail to give candidates the opportunity for a wide range of solutions. That being said, feel free to reach out and ask questions as needed.
- There is no 100% correct solution, be creative! We are just as interested in your approach to problem solving as we are in your actual solution.
- Remember that we'll schedule a debrief interview with you afterwards to discuss the code and ask questions, so you'll be able to explain what you've done!
- Writing style, code comments, and general readability matter despite this being a test!

## Delivery
- Once completed, please include the following:
  1. Your email reply to the customer
  2. Any example scripts/notebooks/collections/etc. you wrote along the way
  3. Your suggested tickets (optionally!)
  4. A brief README summarizing:
  - How much time you spent working on the challenge,
  - Any assumptions you made,
  - Any tricky issues you ran into,
  - Anything else you want us to know about,
  - Any feedback you have on this technical challenge -- we care deeply about our hiring process here at Ethyca, and about the engineers who go through it (that's you!) -- we wholeheartedly promise any feedback will be met with a warm thank you!
- The assignment can be published and shared with us as a .zip file to the Ethyca employee who sent you this task, or via any code sharing platform; please just ensure no secret credentials are disclosed publicly
- We'll review your submission in advance of your debrief interview, and look forward to talking to you about it!

Good Luck!