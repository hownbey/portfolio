The following is a writeup of findings from customer interviews. I published this writeup on an internal blog to pass key takeaways to executives.

# PayPal Champions on documentation

We recently interviewed two bona-fide PayPal Champions about our documentation. This post covers:
* Project background
* Customer profiles
* Key takeaways

## What is a PayPal Champion?

[PayPal Champions](https://developer.paypal.com/docs/community/paypalchampions/) are a select few developers who go above and beyond to advocate for PayPal. They're thought leaders in the developer community who've analyzed the ecommerce market thoroughly. They’ve decided PayPal is the best fit for their customers. In many cases, they're CEOs and founders of small businesses that help merchants solve specific problems.

## Methodology

I decided the documentation itself is a product, so I opted to have an open-ended discussion about the developer portal. This was the right approach - using Champions as generic testers would have lost the nuance of their perspectives as Champions.

Before I interviewed our guests of honor, I prepared a discussion guide with help from our user research group. The discussion guide kept us on track and ensures that other team members can conduct future interviews in a similar way. We can't wait to do this again with other champs.

Ok, on to the findings!

## Champion 1

Champion 1 is the CEO of a service that builds dashboards for PayPal and Stripe integrations focusing on subscription-based businesses. Champion 1 looks exclusively at the REST API reference - no SDK docs. He's so familiar with REST integrations that he doesn't use our integration guides. He accesses our documentation by Googling "PayPal REST APIs" and usually lands on the /api/rest homepage. He uses the left-hand nav to find the API he needs and dives right into the reference.

### Top Insights from Champion 1

* He likes the overall look and feel of the API reference.
* **We should include changelogs or release notes of what changed in each release of the API**.
* **We should include API limitations in the general description of the API.** Currently, he has to dig through the API reference to find the API's limitations, which can be time-consuming and inconsistent across APIs.

## Champion 2

Champion 2 began building ecommerce websites in 2000, right when the PayPal button came out. He's been working with PayPal ever since as the CEO of a small business. Developers often call Champion 2 when they don't know which PayPal integration to pick. Champion 2 uses the entire developer portal and has become familiar with a wide array of PayPal products as he's used many throughout the years.

### Top Insights from Champion 2

* People don't know where to start with PayPal products, but once they find the right integration, they usually don't have much trouble implementing it.
* PayPal integration guides have significantly improved over the past year.
* A confused mind says no. People are more amenable to integrating a product if they understand exactly what they're getting.
* **It's too easy to get lost inside PayPal Developer's information architecture.**
* **There needs to be more clarity in differentiating our REST APIs.**
* **Including error codes and troubleshooting info would be excellent value-adds for our API reference.** Our NVP/SOAP reference had this feature, but our REST reference no longer does.
