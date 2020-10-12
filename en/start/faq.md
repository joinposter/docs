# FAQ:

### How long does the moderation of the application in Poster Marketplace take?

The application is checked for up to 14 days. If you send your integration back for a second review, it will also take up to 14 days.
To speed up the moderation process:

- Test the application before submitting it for review. Make sure it works in all required customer scripts;
- Provide test accesses to your service. Or specify that you do not have test access;
- Record a video tutorial with the process of connecting and working with the integration. It will help the future users to navigate and increase their engagement;
- Clarify the list of Poster customers who are already testing your application;
- Fill out the marketing description of the application, add instructions for users and prices for each region.

### I have a website on Tilda Publishing, OpenCart, Wix, WordPress, uKit or a self-made website. Where do I copy the code and where do I paste it to receive online orders from my website in Poster account?

It doesn’t matter what platform your site is built on. Ask your developer for help or hire a programmer.
We have prepared documentation for [integrating online stores with Poster](/en/docs/v3/market/guidelines/e-commerce).

🔑 Our Application Catalog contains a ready-made application only for [integration with CMS Wordpress + WooCommerce](https://joinposter.com/applications/wordpress).

### Where can I find the integration I’m looking for?

The integrations are located in the [Poster Application Catalog](https://joinposter.com/applications). If you don't find the integration you need there, hire a programmer. We do not make paid modifications for clients. This is the responsibility of our development partners. They can use the API to develop almost any integration.

### Can I use webhooks without creating an app?

You can’t. You need to create an application and connect it to your account.

### How do I set up oauth authorization?

Watch our [webinar to answer this question](https://www.youtube.com/watch?v=CydO5tapXiY&feature=youtu.be&t=397), or [read the API documentation](/en/docs/v3/start/authApi).

### Why is there no Dev/Prod switch on my register?

1. Enable the POS platform in your application settings.
2. Add a Poster account in the developer account to testers, on the register where you do not see the Dev / Prod switch.
3. Connect your integration to the Poster account through the Application Catalog.

### I haven’t found the API for the feature I need. Who do I do?

Write to chat support team or email to <a href="mailto:dev@joinposter.com">dev@joinposter.com</a> - we will suggest a solution to your problem.

### How and where can I get the token if I don’t need a separate application?

Register an account with Poster, open your management console and copy the key in the tab **Access → Integrations → Personal integration**.

### How long is the token valid??

Access token is issued for 2 years

### Is there an emulator for a thermal printer and a fiscal register?

There is no proper emulator for thermal printer or fiscal registrar. To receive bytes only, you can locally raise the server for the printer on port 9100.

### Why do I not receive webhooks?

Check:
1. Whether the URL to which your webhook is sent responds with a status code of 200 and accepts POST.
2. If the URL for webhooks is added in the application settings and when you click on "Check" a green checkmark is displayed.
3. Are you subscribed in the application settings to receive hooks on the required entities?
4. Try simulating sending a hook. To do this, edit the entity you are expecting for the hook in the Poster management console.
5. Check if your application is connected to the account from which you are expecting webhooks.
6. If the app has already been published in the market, please wait for its re-moderation. Changes to settings will take effect after approval from our side.

### How do I validate a phone number for an online order or create a customer card in advance so as not to send you invalid data and not receive an error?

Use the library [libphonenumber](https://github.com/giggsey/libphonenumber-for-php)

### My integration is already published in the Poster App Catalog. Do I need to send it for re-moderation if I made edits in the POS platform or to the code on the application server itself?

No. To apply changes on the POS-platform of your application, you have to run the command: **npm run deploy**.

### My integration is already published in the Poster App Catalog. Do I need to submit it for re-moderation if I change any of the following: marketing description, webhook URL / OAuth / manage, API accesses?

Yes, please submit your application for a second review so that we can check the new data and publish the update.

### Is it possible to send a picture of a product or a dish through API?

No, it isn't possible. You can upload a photo only in the Poster management console in **Products → Products / Dishes**.
