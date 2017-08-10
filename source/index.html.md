---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Web Payments

Korta Web Payments (KWP) is an easy and secure way of accepting creditcard payments. Now there’s no longer need to implement specific programs to accept payments via the Internet.

## How are Korta Web Payments (KWP) implemented?

The merchant applies for a Merchant Agreement along with Web Payments application and gets an account at Korta’s Service Web and signs in. All neccessary information and terms are then registered on the Service

Web by the merchant. Thereafter the merchant can create a web payment form and insert it on his website.

## How is card information secured?

The payment is processed on Korta’s secure website which fully implements all security features neccessary.

KWP website is protected with SSL encryption and the payment process is according to the security standards from the International Payment Card companies, MasterCard International and Visa International or the PCI standard.

When the customer has selected an item on the merchant website or webshop, he clicks the page’s “Payment button”. The Buyer is then forwarded to Korta’s secure website where he finished the

payment. Both the Buyer and the Mertchant will then receive a confirmation via email that the payment has occured and the merchant can then send the purchased item to the Buyer.

## Security issues: PCI DSS – Payment Card Industry Data Security Standard

The KWP Service provides for the highest available security in online payment processing. Numerous security precautions are in place to give the cardholder total confidence in making payments with his creditcard on the Internet. The PCI Certification confirms the security level with extensive internal audits and external security scans.

All information entered, both personal details as well as credit card information, are kept confidential through the use of SSL (Secure Socket Layer) encryption. This means that information can only be exchanged between the cardholder and the sellers web server, and no third party can access this data. The padlock symbol on your browser shows which pages are encrypted and secure.

After the card transactions have been processed, all card information is deleted from the merchant web server and only stored in Korta's highly secured system. The KWP system has been approved according to extensive security requirements and regular security auditing by Visa International and MasterCard International approved auditors.

# Korta Web Payments (KWP) - Overview

When the buyer has clicked on the <b>“Pay at Korta”</b> button he is forwarded to Korta’s secure Web Payment website. On the first page the buyer has to fill out regular info about himself. On the second page, card info is filled out and the payment confirmed. There after the receipt page appears, which is also sent via email to both the buyer and the merchant.

Web Payments are implemented by creating a web payment form, which can be done at Korta’s Service Web or by creating own custom code. This document contains instructions on implementing the Web Payment form using the simplest method to the more complicated code examples which can be used as templates in your own website.

## Merchant pictures and logos in header or site margin on Korta Web Payments (KWP) website.

The merchant can send us his own logo in .gif, .jpg or .png format to place in header on KWP pages. Best is to have the picture 728 pixels wide by 110 pixels height.

Another way is to put a logo on the left margin whichs is 160x100 pixels and hide the header by putting in a image which 1 pixel in height. The merchant has to design the logos/pictures and send them to us.

## Customer is sent (or forwarded) directly to the card payment page.

The merchant can send a specific readonly property <input type="hidden" readonly="Y"> which directs the buyer directly into the card payment input page. This is the perfect way to use whe the buyer has already filled out his personal information (name, address etc.), or if the merchant wants to have his own design for the customer info.

Please note that if this method is used, then you have to make sure that all mandatory fields are filled out, else the page comes up with error which the customer cannot correct.

## Korta Web Payments (KWP) are available in three different main versions:

* Web Payments with easy payment form

* Web Payments with simple coding

* Web Payments with extended coding

# Web Payments with easy payment form generator

It is the easiest way to receive payment for goods or service on the Internet. The Easy Webpayment Form can be created directly on Korta’s Service Web. The Easy Webpayment form is the perfect way when you are selling only separate items or a single event etc without having to use a complicated web application behind it.

In the Service Web the merchant can design a simple Web Payment form with pictures and text along with description, amount, currency and language.

When the merchant has created the web form, then a HTML source code appears which the merchant can copy paste into his own web and start selling items immediately after the Merchant Agreement has been approved.

Confirmations on the ordered items/services are delivered via email to both the buyer and the merchant. The merchant can also view the orders on Korta’s Service Web.

The Payment Webform design tool has the ability to offer quantity plus three optional selections in the Payment form for example: Polo Shirt Qty: 2, Color: Yellow, Size: Large, Logo: “I love Iceland”.

## Technical implementation

All neccessary information about the merchant like item description, amount and currency are included in the Easy Web Payment form along with the security signature which the Web Payment form generator calculates. The security signature is to make sure that invalid alteration of any kind like changing amount, currency or description cannot go undetected.

When KWP system receives payment instruction from Web Payment forms, it processes the merchant info and makes sure that the merchant id, amount, currency and description match with the security signature. If it does not match, the payment will not be processed.

# Web Payments with simple web programming

Simple web programming is intended for those who want to sell more than one item (or service) at a time without having to install a shopping cart system. Merchants who want to go this way will need to web hosting that offers programming in php, asp, perl, java, .net or similar web programming tools. This requires some knowhow in web programming.

## Technical implementation

Implementing such a website could be done as follows:

Step 1: The merchant website offers various items or services. The buyer can pick one or more items and also quantity he want to buy, then he clicks on button or link where he will get a total price.

Step 2: A confirmation page appears where all the items ordered are summarised with a total price and a link or button which is linked to KWP system.

Step 3: The buyer clicks on the payment link or button where he accesses KWP to finish the order by paying with a creditcard.

Both the merchant (seller) and the buyer will receive an email confirmation about the order. The merchant can also access information about the order in our service gateway.

When the buyer has picked the items in step 1 above and pays by clicking on “buy”, a program on the merchant website need to process this info and create a web form with a Web payment button.

The payment button is a HTML form that contains all neccessary information about the merchant, description, total amount and currency. The form also needs to have security signature which ensures that no malicious buyer tries to change payment instructions before it’s diverted into KWP system. The payment button links to KWP system.

### Examples can be found here:
https://netgreidslur.korta.is/?page=samples&lang=en

# Web payment with extended programming

Extended programming is intended for those who want more automation between their web site and KWP system. With extended programming you can connect your web shopping program to KWP. It’s for example possible to sell downloadable items through KWP. With extended programming the customer can be diverted into a confirmation page on the merchant web site when the payment has finished.

## Technical implementation

Technical implementation can be various when you reach this stage of implementing to KWP system.

### Connecting to web based cart system (or web shop)

Web shops can be connected to KWP in a similar way that is done with a payment form that uses simple programming. The key issue is that all information for the payment form contains the info that’s needed to send payment instructions into the KWP system. The payment instructions need to contain info about the merchant, descriptions of the sale items in the cart, total amount and currency.

### Payment confirmation via download URL

The seller (merchant) can add a field in the payment form which shows what link the customer can click on when he has finished the payment. This field is called <b>downloadurl</b>. By using this method, the merchant can add in a link to where the customer can download the purchased digital goods. It’s possible to add a description by sending the the field <b>downloadcaption</b>.

> Example:

```html
<input type="hidden" name="downloadurl" value="https://yoursite.here.is/yourdownload/">
<input type="hidden" name="downloadcaption" value="Download your program here">
```

<aside class="notice">You must make sure that a malicious person doesn’t sneak directly into your confirmation page! That is done by using the downloadmd5 which the KWP system provides and the merchant wep shop program uses to confirm that the customer finished the payment.</aside>

### Customer automatically returns to seller’s web after payment

> Example:

```html
<input type="hidden" name="downloadurl" value="https://yoursite.here.is/yourpath/">
<input type="hidden" name="refermethod" value="POST">
<input type="hidden" name="refertarget" value="_top">
```

Like in above mentioned download URL, the merchant can divert the customer automaticly to a download page (or confirmation page) after he’s finished the payment. This is done by using the <b>downloadurl</b> like above but in addition the field refermethod and refertarget:

<aside class="notice">IMPORTANT NOTE: You must make sure that a malicious person doesn’t sneak directly into your download page (or confirmation page)! That is done by using the downloadmd5 which the KWP system provides and the merchant wep shop program uses to confirm that the customer finished the payment</aside>

### Confirmation for payment sent directly to sellers web via “callbackurl”.

In Korta‘s new version of Web Payments it is now possible to send confirmination on payment directly to the merchant web without going through the buyer‘s web browser. This feature is to make sure that the merchant receives information about a payment if for some reason it hasn’t been confirmed through the customer’s webrowser to the downloadurl page (i.e. browser closed or connection interrupted etc.). Do not use the same URL for the downloadurl and the callbackurl. If downloadurl is skipped, then the customer gets a receipt on Korta’s website, please note that if the SIMPLE/IFRAME version is being used, then all information about the customer are missing and the receipt would appear in the Iframe window in a very compact version. See also below for technical implementation of the callbackurl.

> Example:

```html
<input type="hidden" name="downloadurl" value="https://yoursite.here.is/yourpath/">
<input type="hidden" name="callbackurl" value="https://yoursite.here.is/yourpathforcallback/">
<input type="hidden" name="refermethod" value="POST">
<input type="hidden" name="refertarget" value="_top">
```

Same rules apply for the callbackurl as for the the downloadurl i.e. refermethod POST, GET and REDIRECT. If no refermethod is provided but a callbackurl is sent, then refermethod POST is assumed.

### Examples can be found here:
https://netgreidslur.korta.is/?page=samples&lang=en

## Web Payments in an IFRAME

It is possible to implement a small compact payment form in your own site’s web pages or use your imagination for different designs for what we call SIMPLE look. Please note that when the simple look is used, the KWP system does not receive information about the buyer and sends info about the orders via email after payment.

> Example:

```html
<input type="hidden" name="look" value="SIMPLE">
```

## Options to adjust to your own system

In the next pages you’ll find various options of the KWP System for use with our own wep shop program.

You can also find them on the following link: https://netgreidslur.korta.is/en_usage.html


# API Reference

Payment instructions dictionary

## Payment instructions

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
amount | number(12(20)) | yes | Amount needs to be in form 100.00 (dot for decimal point). 100.00 is the same as 100. Please note that if the field qty is present, then the amount is multiplied with qty to get the total amount charged. If qty is not present then the total amount is same as amount. See also: checkvaluemd5, qty
checkvaluemd5 | string(??) | yes | A security signature that verifies that the payment instruction are originating from the merchant. checkvaluemd5 can only be safe provided that the secretcode is kept totally private between the merchant and Kortaþjónustan ehf. The KWP System verifies that the checkvaluemd5 that comes with the payment instruction is correct. If it is not correct, the KWP System denies the payment instruction and will not proceed. checkvaluemd5 is a digital signature which is created by calculating a md5 hash value of the following variables (amount+currency +merchant +terminal+description+ secretcode) NOTE: As from version 1.2 the string “TEST” must be added at the end of the secretcode when using in our testing environment. This is done to avoid using test checkvaluemd5 string in the production environment. Example md5(amount+currency +merchant +terminal+description+secretcode+“TEST”) More details for programmers can be found in code examples and under md5 security signature. See also: amount, currency, merchant, terminal, description, secretcode, encoding IPMORTANT : The checkvaluemd5 is always in lowercase. Example: Correct: 46b5f42d71da7b2ff2141ecf205358a8 Wrong: 46B5F42D71DA7B2FF2141ECF205358A8  Regex: ^[0-9]{0,9}(\.[0-9]{0,2})?$
currency | string(3) | yes | Currency is always presented using ISO-4217. Example: ISK = Icelandic kronur USD = US Dollar GBP = British Pounds EUR = Euros SEK = Swedish kronur NOK = Nowegian kronur
description | string(255) | yes | Description of sold merchandize /goods or service. A detailed description of what the customer is paying for; The field allows only the html tags <br> (line break). See also: checkvaluemd5
merchant() | string | yes | Main merchant id for the KWP System Issued by Kortathjonustan See also: checkvaluemd5
terminal | string | yes | Merchant second id for terminal. Issued by Kortathjonustan. See also: checkvaluemd5

## Payment instructions (For advanced features, not mandatory)

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
continueurl | string(200) | no | A link which is presented in the KWP System and allows the customer to go back to the merchant web site. If this field is not in place, the KWP system fetches the link that was registered in Korta service web for the merchant info. If nothing is registered, the KWP system uses the info in the HTTP_REFERER variable.
downloadcaption(??) | string() | no | Description or headline for the link that the merchant wants the customer to see when he gets the receipt (it is necessary to use htmlencode on this text so that it appears correctly on the receipt). If this field is not used then the default value “Your download is ready” or similar text in the language that the customer is using. See also: downloadurl
downloadurl(200) | string | no | A link that the merchant wants the customer to be able to click on the receipt after the payment has been made. See also: downloadcaption
callbackurl(200) | string | no | URL where the merchant wants a confirmation about a successful payment sent to his website. When a customer receives a confirmation about his/her payment, then a confirmation is sent to the merchant website with the same information that are sent with the downloadurl (see also downloadmd5 below). After a successful payment, Korta‘s web server will trigger a procedure that sends with POST or GET to the callbackurl and waits for answer (200) from the merchant‘s web server. The merchant‘s web server may receive the downloadurl before the callbackurl and vice versa. The callbackurl procedure is done at the same time the customer receives the auto post form with the downloadurl but will try at least 5 times if no answer is provided by the merchant web server. The callbackurl page needs to echo back a minimum answer of at least one character or word (like „Thank you for your payment“) after successful check on the downloadmd5 security signature. The callbackurl page needs to be implemented to send a confirmation via email to the customer if payment confirmation has not been received through a downloadurl.
lang | string(10) | no | Language , allowed languages are: is = Icelandic en = English
options | string(50) | no | Other optional descriptions. Used if the merchant wants to have options for selections without affecting the checkvaluemd5 value. These options are used for the simple web programming described earlier (page 7) for example color or sizes and qty. Please note as these options are not used to calculate the checkvaluemd5 value, the customer can change them, therefore do not use information there that really matters. Use the description instead.
qty | string(10) | no | Used if the merchant wants the amount to be multiplied to get a total amount for payment. See also: amount


## Payment instructions, needed when form is filled out at seller’s website

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
name | string(50) | yes | Name of customer.
company | string(30) | no | Name of company if applicable.
address | string(30) | yes | Customer address.
address2 | string(30) | no | Additional address if applicable.
city | string(30) | yes | Customer city.
zip | string(16) | yes | Customers address zip code.
state | string(30) | no | Customer state if applicable.
country | string(30) | yes | Customer country.
phone | string(30) | yes | Customer phone number.
fax | string(30) | no | Customer fax number if applicable.
email | string(100) | yes | Customer email address.
email2 | string(100) | no | descCustumer secound email address if applicable.
terms | string | yes | desc ???
encoding | string | no | The character set that the merchant web sends into the KPW System. This affect who characters are shown in the KWP System. The default encoding is in the ISO-8859-1 encoding. You can for example use “UTF-8” if your web system is using the UTF-8 encoding.
look | string | no | With this field the merchant can control what interface KWP System uses to accept payments. If this field is set as “SIMPLE” then a small and compact window appears that can easily be fitted on the seller’s webpage in an iframe. When look=”SIMPLE” is used the behaviour of KWP System changes as follows: - Email is not sent automatically to the customer and the order is not stored in the KWP System. You can change this by setting the field s_order=”Y” - If s_order is not sent with the payment instructions, then the merchant needs to send the field reference. Else the system will show an error and not continue. - See other fields in “Payment instructions (For Simple (iframe) payment window)” See also: s_order, s_showterms, s_showcontinueurl, s_bgcolor, s_fontcolor, s_fontfamily, s_fontsize, reference
readonly | string | no | For those who want to jump directly to the payment pages, set this field to “Y” which causes the KWP System to jump directly to step 2 and asks for card info. NOTE: All fields need to be in place, otherwise the customer cannot continue, where all the fields are readonly and some fields are mandatory. See also: formfields
reference | string | no | Payment reference from merchant. If the merchant wants to get a payment confirmation from the customer, then this field needs to be filled out in order to get the downloadurl posted back to his website after the payment. See also: downloadurl
startnewpayment | string | no | When the customer is diverted to KWP System with a link (or GET) and not POST, then this field
must be sent with the link. Else the KWP System will not show and index page instead of the payment page.

## Payment instructions (For Simple (iframe) payment window)

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
s_bgcolor | string | no | Background color on payment form. Accepts RGB values #aabbcc. Default value is white #ffffff Example: $ff0000 for red, #00ff00 for green.
s_cellpadding | string | no | Use of cell padding in the payment form. Default value is 0
s_cellspacing | string | no | Use of cell spacing in the payment form. Default value is 0
s_fontcolor | string | no | Font color on payment form. Accepts RGB values #aabbcc. Default value is black #000000 Example: $ff0000 for red, #00ff00 for green.
s_fontfamily | string | no | Font type. Must separate values with a comma. Default values are “Arial, Helvetica, sans-serif”
s_fontsize | string | no | Font size. Default value is 12
s_order | string | no | Y or not set. Default is not set and an order is not stored in the KWP System. Therefore a mail is not sent. If an order is to be stored in the KWP System, then the value “Y” shall be sent and mail will be sent to both the customer and the merchant. NOTE: formfields must be set or the order will not be stored. See also: formfields, reference
s_showcontinueurl | string | no | Y or not set. Default setting is that continuerurl is not shown. To show the continueurl, set this value to “Y”. See also continueurl, refermethod, refertarget
s_showterms | string | no | Y or not set. Default settings is link on terms is not shown. To show the link, set this value to <code>"Y"</code>.

## Payment instructions (For sending customer to receipt page on sellers website )

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
authcode | string | no | Added to downloadurl if refermethod is used and equals GET or POST Last 4 digits of card number are added to downloadurl if refermethod is used. See: refermethod
card4 | string | no | This field is sent back if refermethod is used and equals GET or POST Last 4 digits of card number are added to downloadurl if refermethod is used. See: refermethod
cardbrand | string | no | This field is sent back if refermethod is used and equals GET or POST Last 4 digits of card number are added to downloadurl if refermethod is used. See: refermethod
refermethod | string | no | A technique used to send the customer automatically to a confirmation page on the mercant website downloadusr and continueurl (for example when a customer cancels). Possible values are “POST” , “GET” and “REDIRECT”. It is recommended that “POST” is rather used because of a common browser behaviour causes the query parameters (in action property forms) not to return if “GET” is used. If the downloadurl page is not ssl protected, we recommend using the refermethod REDIRECT. By using this method you avoid the “Security Warning” window that appears in both Firefox and Opera browsers. For further information see the section “refermethod REDIRECT” below. Please note that this also has to do how the continueurl works. The customer is sent to the continueurl using the same method. See also: downloadurl, continueurl, refertarget
refertarget | string | no | Used with refermethod. Controls how the customer is sent and links to the variable target for thml form. Default is that targed is not used which corresponds to the same function as using refertarged=”_self”. If a payment windows is used within an iframe then it’s a good practice to “send” the customer out of the iframe by using refertarged=”_top”. See also: refermethod
time | string | no | This field is sent back if refermethod is used and equals GET or POST Time of payment in UTC format dd-mm-yyy hh:mm:ss Sjá: refermethod

## Response codes from web payment system

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
downloadmd5 | string | no | Security signature that the merchant uses to verify that the downloadmd5 is posted from the KWP System and that the payment has been received. This value is added to the downloadurl which the merchant sends with the payment instructions. donwloadmd5 is based a positive confirmation response from the KWP System has the value 2. When the downloadmd5 is created out of the constant 2 along with checkvaluemd5, reference and secretcode (see below). For example when a merchant who sends the the following downloadulr in a payment instruction: donwloadurl=http://mydownload.is/?sessiondata When the customer has paid, the KWP System shows the following: http://mydownload.is/?sessiondata&downloadmd5=aabc32345632dd34 Before the merchant allows the download, he needs to verify the downloadmd5 that the KWP System sends. Security signature can only be safe provided that the secretcode is kept totally private between the merchant and Kortaþjónustan ehf. downloaddm5 is based on the following calculation: md5(htmlencode(2+ checkvaluemd5+reference+ secretcode) ) NOTE: As from version 1.2 the string “TEST” must be added at the end of the secretcode when using in our testing environment. This is done to avoid using test checkvaluemd5 string in the production environment. Detailed info for programmers can be found in code examples and md5 security signature. See also: checkvaluemd5,reference,secretcode

## Secret data between Korta and Merchant

Parameter | Format | Mandatory | Description
--------- | --------- | --------- | -----------
secretcode | string | no | A character sequence that must be kept totally secret by the merchant and Korta. secretcode is used as an
extra parameter when security signatures are calculated from data that’s sent from the merchant to Korta.
Examples of security signatures: checkvaluemd5 og downloadmd5.
secretcode may never appear anywhere like for example a customer’s browser. If unrelated person gets a
hold of this code, then the same can fortify payment instructions sent to the KWP System.
However an unrelated person cannot change the merchant’s bank account or similar, but can cause some
damage at the merchant by sending payment instructions to KWP System for items that do not exist, or buy
items that can be downloaded from the merchant.

## md5 security signature

Methods to md5 encrypt data can be different in various programming environment. Icelandic characters for example need to be treated so that the md5 value is calculated the same way in your system and in the KWP System. In order to md5 encode the same string in both systems a correct conversion needs to be used.

> md5 Encryption

```json
md5(conversion(amount+currency +merchant +terminal+description+ secretcode))
```

It’s possible to calculate md5 value using three types of conversions. Please note when you use ASP or UTF-8 conversion, you must put a prefix in front of the md5 code which tells which conversion is being used.

> PHP

```json
"098f6bcd4621d373cade4e832627b4f6"
```

> ASP

```json
"ASP:098f6bcd4621d373cade4e832627b4f6"
```

> UTF-8

```json
"UTF-8:098f6bcd4621d373cade4e832627b4f6"
```




# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint retrieves a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

