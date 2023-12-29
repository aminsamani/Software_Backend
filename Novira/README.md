### Shopping cart
Create a RESTful API that serves as a stateless shopping cart backend. Handle all relevant
requests such as adding a product to the shopping list, removing a product from the shopping
cart,
Assumptions: Authentication/Authorization would be necessary and we expect it to be handled
based on JWT technology for all the services in the project

### Email Service
Create a service that accepts the necessary information and sends emails. It should provide an
abstraction between two different email service providers. If one of the services goes down, your
service can quickly failover to a different provider without affecting your customers.
Example Email Providers:
- SendGrid 
- Mailgun 
- Mailtrap

All listed services are free to try and are pretty painless to sign up for, so please register your
own test accounts on each.


The aspects of your code we will assess include:
- Architecture: how clean is the separation of concerns.
- Clarity: does the README clearly and concisely explains the problem and solution?
Are technical tradeoffs explained?
- Correctness: does the application do what was asked? If there is anything missing, does
the README explain why it is missing?
- Code quality: is the code simple, easy to understand, and maintainable? Are there any
code smells or other red flags? Does object-oriented code follow principles such as the
single responsibility principle? Is the coding style consistent with the language's
guidelines? Is it consistent throughout the codebase?
- Security: are there any obvious vulnerability?
- Testing: how thorough are the automated tests? Will they be difficult to change if the
requirements of the application were to change? Are there some unit and some
integration tests?
- We're not looking for full coverage (given time constraint) but just trying to get a
feel for your testing skills.

- Technical choices: do choices of libraries, databases, architecture etc. seem appropriate
for the chosen application?
Bonus point (those items are optional):
- Scalability: will technical choices scale well? If not, is there a discussion of those
choices in the README?
- Production-readiness: does the code include monitoring? logging? proper error
handling?