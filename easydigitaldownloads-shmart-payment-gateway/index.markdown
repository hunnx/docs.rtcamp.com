---
title: Easy Digital Downloads - Shmart Payment Gateway
---


## Description:

This plugin is an extension for Easy Digital Downloads, allowing you to take payments through popular Indian service Shmart.

Shmart accepts payments via all VISA & MasterCard debit and credit cards and internet banking of 27 major banks and IMPS payment option of 55+ banks.

Once the order is placed in Easy Digital Downloads and user select option to make payment through Shmart payment gateway then he will be taken to Shmart secure payment page for making payment. After payment process is completed user will be taken back to the main site.

## Installation:

1. Download a plugin from my-account section.
2. Install it like other WordPress plugins.
3. Activate it and go to Downloads -> Payment Gateway tab.
4. Select “Shmart (recommended for Indian users)”
5. Scroll down the page for Shmart Settings, there you can add all the keys/ids related to shmart account and checkout label. Find all the keys from [this section](https://merchant.shmart.in/developer_api_pay_by_shmart) (make sure you are logged in to shmart account).

![selection_032](https://cloud.githubusercontent.com/assets/1140051/10691369/1fb1dba6-79a6-11e5-9a66-44f5a683fea2.png)


## How it Works:

This plugin only work with shmart account [https://shmart.in/](https://shmart.in/). You must have valid merchant ID, API key and secret keys.
First, you can contact to Shmart team and complete all the documentation work to get live account details.

Shmart only accept payment in INR. Hence all the pricing of your product first need to convert into INR and then it will redirect towards shmart pyament page.

For the conversion of any other currency to INR, we are using openexchangerate API (https://openexchangerates.org/) . By default, [https://openexchangerates.org/](https://openexchangerates.org/) provide free API if we are converting USD to INR.
If your store using INR currency only, then openexchange API not required.

If your live store running with any other currency like Euro, Yen, etc. Then you must need to purchase paid API from https://openexchangerates.org/.

## License Key

Once this plugin has been purchased from our [store](https://rtcamp.com/products/easydigitaldownloads-shmart-payment-gateway), you will receive an email with plugin zip file along with license key.

Use that license key under Downloads -> Settings -> License tab and activate it. Which will be helpful to receive future updates of this plugin.

![selection_025](https://cloud.githubusercontent.com/assets/1140051/10630834/6109d91a-77f7-11e5-8eb4-0a1a5efaace7.png)


Note: License key is just to provide future updates and support from our team for the plugin. If license key is not activated on your site, still all the features will work fine.

## Want to use another currency exchange API

We have provided a filter for the same. Check the below sample code:

```
add_filter( 'edd_shmart_currency_conversion', 'alter_edd_shmart_currency_conversion', 10, 4 );

function alter_edd_shmart_currency_conversion( $converted_amount, $amount, $base_currency, $currency ){
	// $converted_amount: Amount after conversion
	// $amount: Actual product amount, may be in USD
	// $base_currency: Base currency, for example INR
	// $currency: INR
	$exchange_rate = 60; // exchange rate for example 1 USD into INR
	$converted_amount = ( $amount * $exchange_rate );
	return $converted_amount;
}
```
## Troubleshooting:

### Error Invalid IP

[![shmart_invalid_ip](https://cloud.githubusercontent.com/assets/7771963/10606506/0b9fc314-7751-11e5-84c6-e7bbe754840a.png)](https://cloud.githubusercontent.com/assets/7771963/10606506/0b9fc314-7751-11e5-84c6-e7bbe754840a.png)

Kindly cross check if the Merchant ID and secret key added in setting page is correct and associate with shmart account where you have provided the same domain name, URL or IP address.

### Invalid Mobile Number:

[![shmart_invalid_mobile_no](https://cloud.githubusercontent.com/assets/7771963/10606530/2b72ae5e-7751-11e5-8cdc-a985f8d69658.png)](https://cloud.githubusercontent.com/assets/7771963/10606530/2b72ae5e-7751-11e5-8cdc-a985f8d69658.png)

Kindly check if the mobile number is added by customer or not. Also verify that there should not be any special character in mobile number like +91.

The contact number is required fields by shmart payment gateway, hence in plugin we have implemented.

If you are facing any other issues related to plugins, feel free to create a premium support ticket [https://rtcamp.com/premium-support/](https://rtcamp.com/premium-support/).

If you are getting errors related to shmart API or openexchnage, please try to contact respective support team.
