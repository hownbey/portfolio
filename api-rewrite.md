# Before and after - API description rewrite
  
This redesign resulted in a 5% boost in API adoption, which translates into tens of thousands more people using this API. The redesign proves more customers adopt a product when they understand what it does. 

## Before

**I can’t emphasize this enough: I didn’t write this!**

> Payment Tokens APIs can be used to securely store payment methods in the PayPal vault rather than within your own data store.
> 
> Setup Tokens creates temporary tokens that are created for caching payment methods from client environment (Ex Browser) and when a Vault requires approval from your customer before being vaulted. Setup tokens provide your customer a way to verify and authenticate the payment method being stored in the Vault. Setup tokens can be used in a transaction or converted to payment method token only once.
> Payment Tokens creates a permanent payment token that is reference to vaulted payment method. A payment token can be repeatedly used checkout and recurring transactions.

## After

I redesigned the previous API description to:
* Reduce words by 23%. 
* Increase the Flesch reading ease score from 45 to 58.

> The Payment Method Tokens API saves payment methods. After a payer agrees to save a payment method, the payer can: 
> * Check out without entering details.
> * Pay without being present; for example, subscribe to goods or services.
>
> The API associates a payment method with a temporary setup token. Pass the setup token to the API to exchange for a permanent token.
>
> The permanent token represents a payment method saved in the vault. You can use this token repeatedly for checkout and recurring transactions such as subscriptions.

You can read the [API reference description here](https://developer.paypal.com/docs/api/payment-tokens/v3/).
