# Sendgrid

- To create and configure a Twilio SendGrid account using Microsoft Azure.

## Create an Azure Subscription

- To get started with Twilio SendGrid and Azure, visit the Azure Portal home page. You will need to sign in or create a Microsoft account.
- A new page will load, listing your current Azure subscriptions. You can add a new Twilio SendGrid service to an existing Azure Subscription or Select +Add to create a new Azure Subscription. For more information about Azure Subscriptions and billing, see the Azure docs for how to "Create an additional Azure subscription."
- A form will load with a Subscription Name field. You must add a name
- Once the Subscription is created, you will see it listed on the Subscriptions page. If you do not see the Subscription, try refreshing the list.

## Create a Twilio SendGrid account

- From the Azure portal home page, select Marketplace under Azure services. If you do not see the Marketplace icon, you can search for it by selecting More services.

- The Azure Marketplace provides many services, including the Twilio SendGrid email service. You can find it by searching for "Twilio SendGrid." You will also find it under Software as a Service (SaaS).
- Click the Twilio SendGrid resource to load a page where you can select your account tier. You can start with a free account and upgrade as your sending needs change

## API keys

API Keys authenticate your application, mail client, or website with Twilio SendGrid services. Unlike a username and password, API keys are scoped to provide access only to the services you select. You can also delete and create API keys without impacting your other account credentials. For these reasons, Twilio SendGrid requires you to connect to its services using API keys.

## Create an API key

- In the Twilio SendGrid App, navigate to API Keys in the Settings menu, and select Create API Key.
- A modal will open where you can create your key. You must name the API key — we recommend something that will clearly differentiate the key from others you may create in the future.

You must also select the type of key you want to create. Twilio SendGrid provides three types of API key:

- Full Access
- Restricted Access
- Billing Access

## Use an API key

Twilio SendGrid's v3 APIs expect an API key to be passed in an Authorization header as a Bearer Token. See the Twilio SendGrid v3 API reference for help using your key to send your first email.

The Twilio SendGrid helper libraries all provide a method to set your key, handling the authentication via Bearer Token for you. See the Twilio SendGrid developer documentation for helpful code examples and links to helper libraries in C#, Go, Java, Node.js, PHP, Python, and Ruby.

When using Twilio SendGrid’s SMTP integration, you will set your API key as a password via Basic Authentication. Your username must always be the string, “apikey.” Using the account credentials (username and password) you set up through Azure will fail, so be sure to set your password to the 14 digit API key provided by the Twilio SendGrid App. Your account credentials are separate from the credentials used to authenticate with Twilio SendGrid’s APIs and SMTP services.

```
username: "apikey"
password: <your-api-key>
```
