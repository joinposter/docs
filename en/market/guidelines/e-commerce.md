# Integration with a website for online ordering

If you have a website, mobile app or chatbot where your clients can order food, setup orders sync to POS. 
The example of perfect integrations is a website builder — [Poster Shop](https://joinposter.com/en/applications/poster-shop-production).


## Connection

### Integration with your own website

To send orders to Poster you will need an **access_token**. 
Get it in the management console on **Access** → **Integrations page**, in front of **Personal Integration** application.

☝️ Don’t create developer account if you don’t need to track when orders have been accepted or declined on a register.

☝️ Usually, you don’t have to sync a menu, there is enough to match products IDs from Poster with yours and hardcode it on your webiste.


### Integration for marketplace

Clients shouldn’t enter their tokens or do the manual job, 
so you have to create an application in the [developer account](/login) and implement [oAuth authorization](/en/docs/v3/start/authApi) to get the access token.


## Menu sync

To send the order to Poster you have to know the mapping between products in your system and products in Poster. 
There are a few solutions on how to do that:

1. Delete all products from your service and replace it with a menu from Poster
2. Match products by name and give a user interface to do the mapping between products

Choose one of those solutions and use:

1. [menu.getProducts](/en/docs/v3/web/menu/getProducts) method to get all products from Poster. You will need `product_id` to send the order to Poster.
2. [menu.getCategories](/en/docs/v3/web/menu/getCategories) method to get all product categories.
3. Subscribe to [webhooks product and dish](/en/docs/v3/web/webhooks) in order to:
    - Update prices or products name, when it changes in Poster
    - Add new product
    - Remove products in your website when the client deletes it in Poster
4. In each webhook, there is an `object_id` filed which is equal to `product_id` of changed product. 
Use [menu.getProduct](/en/docs/v3/web/menu/getProduct) method to get all the information about the product.

☝️ If you don’t want to set up your database to save mappings, use [product extras](/en/docs/v3/web/application/setEntityExtras).


## Orders sync

Use [incomingOrders.createIncomingOrder](/en/docs/v3/web/incomingOrders/createIncomingOrder) method to send the order to Poster.

☝️ If the order has already been paid, send `payment` parameter with paid sum. When cashier will close this order he will see total sum to pay 0$.

Subscribe to [incoming_order webhook](/en/docs/v3/web/webhooks), and you will receive a notification when cashier:
 - Decline order
 - Accept order
 - Close order

You can sync all these events with your system. For example, when cashier close online-order you will get the webhook and can send an email to the client that his order is ready.
