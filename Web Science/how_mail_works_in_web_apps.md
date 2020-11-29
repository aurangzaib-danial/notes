


# How mail works in web apps?
Mail servers are different than web servers. Interface for managing email accounts and accessing inbox on them is provided by mail service providers. It is something we do not build.

Web servers send emails to mail servers and then the mail server is responsible for delivering it to the recipient.

Using mail servers for hosting companies delivering emails to our customers is not a good idea because these mail server IP's might not have a very good reputation and the email sent through them might be put into spam folder by the receiver's server. **This is sole reason, why we use services like _sendgrid_ for delivering our emails**. 

**Receving emails**
We configure our domain's dns email lookup to use our mail server. Whenever somone sends an email that is based on our domain, it actually connects with our mail server instead of our web server.
