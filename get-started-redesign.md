# Increasing user satisfaction by 100% 

This redesign took the user satisfaction score from a 2 to a 4 out of 5 on a page that gets over a million visits every year. We also decreased time-to-first-click by a full 60 seconds. Check out the before and after and read commentary about what I did.

## Before 

![API get started page before redesign](https://github.com/hownbey/portfolio/blob/main/img/before.png)

## After

![API get started page after redesign](https://github.com/hownbey/portfolio/blob/main/img/after.png)

## Explanation of changes

For content enthusiasts, here's a play-by-play of the changes I made.

### The old intro

The doc started with a clammy handshake: “The PayPal REST API is organized around transaction workflows, including payments, subscriptions, invoicing, and disputes.”

Let's paraphrase this: “PayPal REST APIs do money stuff.” Call the papers; who knew? The next sentence has some filler on how REST APIs work. So as an external developer, I've read two sentences that tell me “Our APIs do stuff. Here is how REST APIs do stuff generally.” Nothing actionable here.

There's finally an actionable step in the third sentence: create an account on the Developer Dashboard. Then, generate the things. No, we're not going to tell you how to generate the things or tell you what they are.

Time for a Brick of Text (TM). Something something accounts. Tl;dr - I'm happy for you, or sorry that happened.

Oh cool, a Run in Postman button! If I click it, it takes me to a Postman collection! But where is the documentation for how to use this? I'm marooned!

### The account types section

Use sandbox accounts to test your app. Sorry, what are sandbox accounts? Ok, I'll need both both (sic) personal and business sandbox accounts? 

Suddenly a useless table busts in like the Kool-Aid man.

And that's pretty much the end of the page.

We figured our devs had some lingering questions. How do you get an access token? What is the sandbox? How do you get sandbox credentials?

### The new intro 

We start with telling the dev how our APIs authenticate and what they return. We're specific, concise, and upfront that you can only test US integrations.

Next, we provide a link to Postman for the types who'd rather do stuff than read stuff. Go on, be your best busy self. We also added documentation inside Postman so users are no longer marooned.

We put important information about a PayPal Business account in a big red box so you can't miss it. We also made the information as digestible as possible in two bullet points. By the time you skim it, you're done reading it. It really is one heck of a warning box. This was the artist formerly known as Brick of Text (TM).

### Get client ID and client secret

We explain exactly what a client ID and secret are, what they do, and how you use them. Then we give clear, step-by-step instructions for how to grab them from the Developer Dashboard. These instructions weren’t on the old page.

### Get access token 

Also missing from the old page - instructions for getting an access token and an explanation of what an access token is. So, we put information on getting an access token via cURL and Postman. Then we hit the devs up with a sample response. Expectations set.

### Get sandbox account credentials 

We round off our page with some important info about the sandbox. First off, we did some level-setting about what a sandbox is. “The PayPal sandbox is a test environment that mirrors real-world transactions.” Short and sweet, almost pithy. Top it off with step-by-step instructions for how to get sandbox credentials for personal and business accounts, and boom. You've got everything you need to get started.

We liked our redesign. Based on customer satisfaction scores, our audience liked it too.
