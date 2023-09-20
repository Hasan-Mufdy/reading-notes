# Payment Processing

## How to read Technical Documents as fast as possible

1. Establish why you are reading it

If you don't know what you are trying to find, you'll either fall asleep or mindlessly stare at the words in each section. Are you reading for familiarity? Do you need to figure out how to do something specific? What exactly is the task you need to accomplish?

2. Get an overview of the content and structure of the document

Read the cover, table of contents, and any introduction chapter (5 mins max).

3. Take 30s to 2 minutes to scan the rest of the document. Click on the scrollbar and just breeze through all the pages. Just look at the pictures, tables and diagrams. Look for things that look familiar and that you will understand immediately. APIs, schematics, flow charts, block diagrams. Read the captions under the pictures.

4. If you want, stop at the interesting parts and take a deeper look. Stop when it gets boring.

5. Look at the table of contents again. You'll have a deeper understanding of the document after you look again.

6. Choose what to read next based on interesting-ness or usefulness. If there's nothing useful, close the doc. You can say that you've read it from cover to cover.

## How Does Online Credit Card Processing Work?

### Payment Gateway

The Payment Gateway is responsible for sending the credit card to the appropriate Internet Merchant Account over secure online channels. The approval or decline of the transaction, however, is actually performed by the Merchant Account. It is helpful to think of the Gateway as a router that sends the credit card information to the appropriate account. It is also responsible for fraud checking and maintaining reliable links with the merchants.

## Authorize.Net .NET SDK

#### TLS 1.2

### Installation

To install the AuthorizeNet .NET SDK, run the following command in the Package Manager Console:

```
PM> Install-Package AuthorizeNet
```

### Registration & Configuration

Use of this SDK and the Authorize.Net APIs requires having an account on the Authorize.Net system.

### Authentication

To authenticate with the Authorize.Net API, use your account's API Login ID and Transaction Key. If you don't have these credentials, obtain them from the Merchant Interface. For production accounts, the Merchant Interface is located at (https://account.authorize.net/); and for sandbox accounts, at (https://sandbox.authorize.net).

After you have obtained your credentials, load them into the appropriate variables in your code. The below sample code shows how to set the credentials as part of the API request.

To set your API credentials for an API request:

```
ApiOperationBase<ANetApiRequest, ANetApiResponse>.MerchantAuthentication = new merchantAuthenticationType()
{
    name = "YOUR_API_LOGIN_ID",
    ItemElementName = ItemChoiceType.transactionKey,
    Item = "YOUR_TRANSACTION_KEY",
};
```

Never include your API Login ID and Transaction Key directly in a file in a publically accessible portion of your website. As a best practice, define the API Login ID and Transaction Key in a constants file, and reference those constants in your code.
