# Code block troubleshooting

The engineering team rolled out Gatsby React code blocks that toggle between code languages. It's a cool feature, but there's one catch. Broken code blocks create a 404 "Not Found" error on the page, and the system won't say why. If you add or change a code block and get a 404, this guide will help you get unstuck.

## Check your markdown in prettier.io

Copy your markdown and paste into [prettier.io](https://prettier.io/playground). Set the `--parser` to **mdx**. See if there are any syntax errors that appear in the right column. Prettier doesn't tell you where the errors are exactly so you might have to do some search work in your document.

Sometimes the error messages in Prettier are useless. Sometimes a page passes in Prettier but still 404's, and vice-versa. That's ok; that's what the rest of this guide is for.

## Escape dollar sign and back tic characters

"Escape" is a fancy way of saying "put a backslash in front of." The most notorious offenders are the dollar sign and back tic in JavaScript. Make sure all instances of `$` and <code>&#96;</code> in your code blocks have a backslash in front of them:


```
return fetch(\`/api/paypal/orders/\${orderID}/capture/
```

The backslash tells Gatsby to display the character instead of reading it to render the page. When in doubt, put a backslash before a funky character in the code block and see if that makes the page work.

## Align code with the left-hand side of the block

Code block markup looks like this:

```
<CodeBlockWrapper>
<CodeBlock className="language-json" children={`
PASTE YOUR CODE SAMPLE BELOW AND THEN DELETE THIS LINE. IT'S ALL CAPS SO YOU DON'T FORGET TO REMOVE IT. EMOJIS :) ;) :D
`}/>
</CodeBlockWrapper>
```

Paste the code sample flush with the left-hand side of your code editor. This gives the code proper indentation.

```
<CodeBlockWrapper>
<CodeBlock className="language-html" children={`
<script>
  // Render the eligible PayPal buttons within the #paypal-button-container
  paypal.Buttons().render('#paypal-button-container')
</script>
`}/>
</CodeBlockWrapper>
```

## Clear empty lines in the code

Empty lines will 404 your page! Remove the empty line and put a `\n` instead.

```
"experience_context": {
       "return_url": "https://example.com/returnUrl",
       "cancel_url": "https://example.com/cancelUrl"
     }, \n
     "purchase_units": [{
       "amount": {
         "currency_code": "USD",
         "value": "100.00"
       }
```

## Remove smart quotes

Smart, formatted single and double quotation marks cause errors in your code. Find and replace them with plain, straight single or double quotes. This applies outside your code, too. There is no need for smart quotes in our docs, period.

These are smart quotes, and they ruin your page results: “ ”, ‘ ’

These are straight quotes, and they are The Way: " ", ' '

Smart quotes often show up when the source material is pasted from Word. Charming.

## Fix horizontal scrolling code blocks

Sometimes, the code block displays all the code in one long line. The user has to scroll horizontally to see the code - ew. Fix this issue by removing line breaks and replacing them with `\\\n`. It's an eyesore in our source code, but displays properly for the user.

This applies only to cURL headers. You don't have to do this with the JSON that follows.

```
<CodeBlockWrapper>
  <CodeBlock
    className="language-bash"
    children={`
curl -s -X POST https://api-m.sandbox.paypal.com/v1/oauth2/token \\\n -u 'CLIENT_ID:CLIENT_SECRET' \\\n -H 'Content-Type: application/x-www-form-urlencoded' \\\n -d 'grant_type=client_credentials' \\\n -d 'response_type=id_token' \\\n -d 'target_customer_id=CUSTOMER-ID'
`}
  />
</CodeBlockWrapper>
```

## Set the code block language correctly

Make sure the language inside your block matches the CodeBlock className.

### Bash

If something has a curl header in it, it's "language-bash", even if there's json after:

```
<CodeBlockWrapper>
<CodeBlock className="language-bash" children={`
  curl -v -X POST https://api-m.sandbox.paypal.com/v2/checkout/orders
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer Access-Token' \
  -d '{
    "intent": "CAPTURE",
    "purchase_units": [{
      "reference_id": "d9f80740-38f0-11e8-b467-0ed5f89f718b",
      "amount": {
        "currency_code": "USD",
        "value": "100.00"
      }
    },
`}/>
</CodeBlockWrapper>
```

### HTML

Code is usually "language-html" if it has open and close tags, like <code><script></script></code>.

There can be a lot of code inside script tags. Don't let that trip you up.

```
<CodeBlockWrapper>
<CodeBlock className="language-html" children={`
  <script>
    // Render the eligible PayPal buttons within the #paypal-button-container
    paypal.Buttons().render('#paypal-button-container')
  </script>
`}/>
</CodeBlockWrapper>
```

### JavaScript

Node.js samples are also language-javascript.

```
<CodeBlockWrapper>
<CodeBlock className="language-javascript" children={`
  // Check eligibility for advanced credit and debit card payments
  if (paypal.HostedFields.isEligible()) {
    // render hosted fields
    paypal.HostedFields.render({
      //This sample function returns the order ID
      createOrder: () => {
        // logic to return an order ID from your server. Refer to Step 3 for the code snippet to Create Order from your server
      },
      fields: {
        number: {
          selector: '#card-number',
          placeholder: 'card number'
        },
        cvv: {
          selector: '#cvv',
          placeholder: 'CVV',
        },
        expirationDate: {
          selector: '#expiration-date',
          placeholder: 'mm/yyyy'
        }
      }
    }).then(function(hf) {
      document.querySelector('#my-sample-form').addEventListener('submit', (event) => {
        event.preventDefault();
        hf.submit({
          // pass the value of the checkbox when submitting the advanced credit and debit card payments instance
          vault: document.querySelector('#save').checked
        }).then(function(payload) {
          // Make a call to capture the order (payload.orderId) here
        });
      });
    });
} else { /* Handle experience when advanced credit and debit cards is not eligible */ } `}/> </CodeBlockWrapper>
```

## If all else fails...

This is war. Cut each code block one by one. Each time you cut a code block, save your page, and refresh in localhost. When the page no longer displays a 404, you've found the problem. If you're doing this, you're out of options, you desperate individual, you. We've all been there. We'll sip a tasty beverage in your honor.
