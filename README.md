# Coding Test: Pricing Service

Thank you for taking the time to complete our coding test. Your challenge is to recreate a hypothetical version of our internal pricing service. 

You are free to **use a language (and framework) of your choosing** - we want to get a feel for how well you translate requirements into code, so pick one you're familiar with. 

Feel free to **spend as much or as little time as you'd like** as long as the specified functionality is complete. As a ballpark, the test should take around 90 minutes of development time.


## Building the basic API

Given the included [pricing data](./pricing.json), build a RESTful API endpoint that will accept requests like the one shown below and return pricing information for the order:

```json
{
	"order": {
		"id": 12345,
		"customer": {
			...
		},
		"items": [
			{
				"product_id": 1,
				"quantity": 1
			},
			{
				"product_id": 2,
				"quantity": 5
			},
			{
				"product_id": 3,
				"quantity": 1
			}
		]
	}
}
```

The returned data structure should include:

* the total price for the order
* the total VAT for the order
* price and VAT for each item in the order

Data structure for the response is up to you.

Note that the monetary values in the pricing.json file are in pennies GBP and the results should be likewise. Any rounding should use standard arithmetic rounding to the nearest penny.


## Going international

In this hypothetical universe we've decided to launch tails.com overseas, and want the pricing service to be able to return equivalent prices in any given currency using the latest available exchange rate data.

Expand the API to allow the currency to be passed in as part of the request, and return the equivalent price in that currency. How that currency code is passed in is up to you. Use a currency conversion rate API like [fixer.io](http://fixer.io) to get the latest exchange rates as part of your solution. (Hint: you might want to think about how to cache that data).

For the purposes of the test, assume the same VAT rates apply to all countries and currencies. (If the world actually worked this way, I think I'd still have hair on my head.)


## Testing

If you haven't been doing so as you've gone along, write appropriate tests in the test framework of choice for the pricing logic. If you don't have time, just tell us how you'd go about testing that this logic works as intended (e.g. what level of testing, what sorts of test cases, etc.).


## Submitting

Once you're happy with your code, zip it up and email it back to us along with answers to the following questions:

1. What command do we run to start your server? 
2. If you had more time, what improvements would you make if any?
3. What bits did you find the toughest? What bit are you most proud of? In both cases, why?
4. What one thing could we do to improve this test?
