## Application debugging

### PC debugging

In a container with real users, your application will be loaded from a `platform.joinposter.com` subdomain. 
To update the application, you have to make a deploy and restart Poster on a register.
However, it is not convenient to do in the process of development; you have to update the application much faster.

To do this: 

1. In your [developer account](/en/login) on **Users and roles** page enter a subdomain of testing account
2. On a register in top right corner press **</>**. You will see Platform settings window.
3. In platform settings popup switch to **Development** mode

<img src="/img/site/docs/pos-platform-dev-mode.gif" alt="Example how to switch into development mode">

In development mode bundle will load but your local computer at `http://127.0.0.1:8080/bundle.js`. 
You can use your web server, or `webpack-dev-server` if you use our boilerplate for development.


From `webpack-dev-server` at our boilerplate, your application will automatically reboot in the container when you change its source code. 
It will allow you to quickly make updates and get feedback.

You can use Chrome Developer Tools for debugging. 
All `console.log` in your application’s container are displayed on the Poster web version console.

### Debugging on iOS, Android tablet

To debug on iOS and Android go to Platform settings window and enter your PC IP address with `webpack-dev-server` launched. 
Bundle will be loaded from that IP.
