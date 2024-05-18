##  Short(URL) King

Your challenge is to design a system similar to https://tinyurl.com/ named https://short.king/.

### API
The user should be able to hit your api on the following routes.

POST `/create?url=<..long_url..>`
> Return a `201 Created` status code, along with the shorter URL hash.

> Return a `200 OK` status code if the long url already exists, along with the shorter URL hash.


GET `/<..short_url..>`
> Return a `301 Permanent Redirect` status code which redirects the user to the corresponding longer url

> Return a `404 Not Found` status code if the `short_url` has not been generated

GET `/`
> Return a form to create an shortened url

## Additional Challenges 
The following questions are designed to emulate real problems a team may encounter. They are good things to consider but are not expected to be solved in this challenge. 

"Premature optimization is the root of all evil" - some guy

#### Your website is getting incredibly popular. So much so that you are generating between `200-300` new short urls per second. 
> 
> How do you ensure your system will not run out of short urls while still keeping the url size small?


#### You found out that your site wasnt getting popular, it was being **attacked**! Attackers have orchastrated a DDoS attack by generating a series of fake urls from a select few IP Addresses.
>
> How can you minimize the number of fake urls being generated while not disturbing your regular users?

#### Okay this time its for real, your website is getting popular. This time you find that the number of generated keys are **growing** over time.
> 
> What is your strategy for scaling? What solutions exist, and what are their strengths and weaknesses?
