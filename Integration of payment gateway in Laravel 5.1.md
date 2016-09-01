---
title: Integration of payment gateway in Laravel 5.1
tip-number: 8
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Integration of payment gateway in Laravel 5.1

---

To integrate Payment Gateway in Laravel 5.1, we need to follow the below steps.

Laravel has a package called “IndiPay - Indian Payment Gateways”  which supports payment gateways like CCAvenue, PayUMoney, EBS, CitrusPay, InstaMojo.

Step 1: First we will Install the package through composer.
```php
	 composer require softon/indipay
```
Step 2 : Add the service providers to the app.php file in config folder.

```php
	'Softon\Indipay\IndipayServiceProvider',
```

Step 3 : Add alias for the Facades to config/app.php file

```php
	'Indipay' => ‘Softon\Indipay\Facades\Indipay’,
```

Step 4 : Then, publish the vendor to have a config file in Laravel config folder.


How to implement it in our project?

It is always a best practice to keep configuration variables in .env file. Update the .env file with the appropriate Gateway Keys.

Then, edit the config/indipay.php file and set the Gateway name that we used in .env file.

Steps to Initialise the payment request with a Controller.

Add Facades in the beginning of the controller
	 
```php	 
	use Softon\Indipay\Facades\Indipay;  
```	

After that in the method where the payment has to be achieved, include the following code:

```php
	$parameters = [
                'txnid' => ‘XXXX’,
                'redirect_url' => ‘XXXX’,
                'purpose' => ‘Testing’,
                'amount' => 2500,
                'buyer_name' => ‘XXX’,
                'allow_repeated_payments' => <true/false>
            ];
```            

We need all the above POST parameters to successfully do the payment transaction.

After specifying the parameters, you need to two more lines to make payment request.

```php
	$order = Indipay::prepare($parameters);
	return Indipay::process($order);
```

The above line of code will generate the below form,

```php
	<html>
	<head>
    	<title>IndiPay</title>
	</head>
	<body>
    	<form method="get" name="redirect" action="{{ $longurl }}"></form>
	    <script language='javascript'>document.redirect.submit();</script>
	</body>
	</html>
```

that will be submitted automatically due to the statement return.

And then the page will be redirected to the specified Payment Gateway that we have configured. After the successful completion of the money transfer, it will be redirected to the URL which we have specified in the parameter list.


To get the response from the Payment Gateway, we can use the below lines of code to get the status of transaction whether success or failure

```php
	public function response(Request $request)
    	{
       		$response = Indipay::response($request);
        	dd($response);
    	}
```    

Sample response

```php
	{
	    "payment_request": {
	       	"id": "92e58bd771414d05a5e443b0a85f8b43",
	       	"phone": "+919999999999",
	      	"email": "foo@example.com",
	      	"buyer_name": "David Doe",
		...more properties...
	       	"payments": [
	   		{
	       		"payment_id": "MOJO5a07005J30161862",
	       		"quantity": 1,
	       		"status": "Credit",
	       		…more properties
	   		}
	       	],
	    },
	    "success": true
	}
```

Each payment response has a key “status” if the value of the key is "Credit" then the payment was successful otherwise it has failed.
