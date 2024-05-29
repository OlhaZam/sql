# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
My answer:
Both Type 1 (overwrite changes) and Type 2 (retain changes) approaches for storing customer addresses have privacy implications. Type 1 is simpler and stores less data, reducing the risk of data breaches but lacking historical accountability. Type 2 retains historical data, useful for audits and resolving disputes but increases the amount of sensitive data that needs protection. The choice depends on business needs, regulatory requirements, and the balance between historical data importance and privacy risks. Robust security measures and clear data policies are essential in either case.
```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
My answer:

1. Employee shifts logic.
 My solution involves a separate EmployeeShift table to manage shift assignments with specific dates, providing detailed historical tracking. The AdventureWorks Schema solution integrates the ShiftID directly into the Employee table, simplifying shift management. I believe, my solution offers the advantages of historical tracking and flexible scheduling but is more complex and requires additional table management. In contrast, the AdventureWorks Schema solution is simpler and easier to manage, directly updating current shift assignments but lacks historical tracking and flexibility. If historical tracking and flexibility are crucial, than my solution is better; if simplicity and ease of use are more important, the AdventureWorks Schema solution is preferable.

2. Book/Product price storage
My solution of the book price stores the current book price directly in the Book table, while the AdventureWorks Schema solution uses a separate PriceListHistory table to track price changes over time. Storing the price in the Book table is simpler and provides faster access to the current price, but it lacks historical tracking and flexibility. On the other hand, the PriceListHistory table allows for detailed historical tracking and flexibility in managing price changes over time, which is useful for auditing and dynamic pricing, but it adds complexity and may impact performance due to additional joins and data management. If historical tracking and price management flexibility are crucial, the PriceListHistory table is better; if simplicity and performance are more important, storing the price in the Book table is preferable. 

```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
