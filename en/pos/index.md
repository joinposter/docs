# POS Platform: Introduction

**The Point-Of-Sale Platform (POS Platform)** is a technology that allows external developers to expand the functionality of the Poster cash solution. Use the Point-Of-Sale Platform for applications a waiter or a cashier deals with. For example:

- **Integration of external loyalty systems with Poster.** The cashier authorizes a customer by his phone number or QR code and suggests writing off his points.
- **Integration of IP telephony and automatic telephone stations with Poster.** The cashier receives an incoming call and immediately sees the customer’s card at the register including his name, address, and latest purchases.
- **A chat with the floor section employees.** The owner writes in the management console about an incentive program updates and the location news. The message comes to the register; every cashier should check it out.



## Technologies

Poster has a hybrid architecture; the bulk of the business logic of the application is written using web technologies. Applications on the register platform run Javascript. You can write an application in any language compiled in JS (CoffeeScript, TypeScript). An application is loaded into the system as a single JS file (bundle).

All resources that use the application (CSS, images, typefaces, sounds) must be included in the bundle. To do this, you have to use bundlers. In the examples that you can find in the documentation, the webpack bundler is used.

A JS file with an application is launched inside a special **container** at the register. **The container** is an Iframe with built-in methods enabling the application interaction with Poster. The application in the container is cached at the register and can be launched and run without the Internet connection.

To create an application interface, you can use any framework or library. For example, Backbone, VueJS, Angular, React. The Poster register interface is written on React, so if you are writing an app using React, you can use some ready-made components that are customary for Poster users. When working with other frameworks, you will have to implement all the components on your own or install external plug-ins.


# POS Methods: Methods

In the **container** , a global `Poster` object is available to the application. The object contains a set of methods for signing up for events, working with data collections and interfaces in Poster.
