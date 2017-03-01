 Deployment slots are a feature of app services, which comes with web apps, API apps and mobile apps. These enable you to set up environments that you can use to test your application in. 
  <br/> <br/>
 Before we get into what they are, let's talk about why would you use deployment slots? 
 You can use deployment slots to confirm changes to your application in preproduction. This enables you to see how your changes behave in the cloud, before you promote them to production. They also enable you to test in production. You can actually route a percentage of production traffic to a deployment slot containing the changed we application. 
  <br/> <br/>
 You can deploy a new web application with virtually no down time. Once you are happy with the application in the deployment slot, you can swap it with your production web app, resulting in the new version being up and running instantly.
  <br/> <br/>
 Also, you can easily revert back to the previous version of your web application if, for whatever reason, you're not happy with the result. 
  <br/> <br/>
 So what is a deployment slot?
 Suppose I have a web app running. It has the URL of website.demo. I can now deploy my application in the web app. This is now my production environment. Suppose I create a deployment slot for my web app. It is, in fact, an actual web app running alongside of my production web app. It has a different URL though, in this case website.staging.demo.
 As with any web app, I can deploy my app in it. In this case, I deploy a changed version of my web application in it. I can now use the deployment slot to test against, and make sure that the changes are to my liking. I can even route some of the production traffic to my deployment slot to see how users react to the new changes. Once I'm happy with the changes, I can swap the deployment slot with my production web app. You do this by executing an operation that is actually called swap. By doing this, Azure swaps the virtual IP addresses assigned to the slots, and it makes sure that the source slot is warmed up, meaning that it responds immediately when somebody navigates to it. Because of this the swap is seamless and causes virtually no down time in production.
 <br/> <br/>
 
 If I'm not happy with my changes in production, I can simply swap back using the same process. Next to just the staging deployment slot, I can have others, like a dev and test environment. In effect, I could set up my whole deployment setup using web apps. Depending on the pricing tier of your web app, you can create up to 19 deployment slots next to your production web app. Some things to note about deployment slots. A deployment slot is a fully-fledged web app. This means that it incurs costs like a normal web app and has things like settings, configurations, etc, which you can change to be different than the production web app. You cannot scale a deployment slot that is not your production web app. This means that you cannot increase the amount of instances in which the deployment slot is running. This also means that a deployment slot might not be the best environment to do performance testing on. When you swap a deployment slot with another slot, you swap the virtual IP address. If you use this IP address for anything, like custom domain name binding, you need to be aware of this. 

 <br/> <br/>
