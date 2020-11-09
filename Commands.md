
#### Install Helmet

        npm install helmet [This will install latest version]
    
#### Hide Potentially Dangerous Information use:-
   
        helmet.hidePoweredBy() [Middleware can handle or make sure to remove X-Powered-By header]
        app.use(helmet.hidePoweredBy({ setTo: 'PHP 4.2.0' }))  [Setting header to something else intentionally] 
        
#### Mitigate the Risk of Clickjacking
    
        helmet.frameguard() [Along with configuration object {action: 'deny'}]
        
 It has 3 options -> DENY, SAMEORIGIN, ALLOW-FROM 
 
 #### Mitigate the Risk of Cross Site Scripting (XSS) Attacks
       
        helmet.xssFilter() [Tp sanitize input sent to the server]
        
 #### Avoid Inferring the Response MIME Type by adding method
 
        helmet.noSniff()
       
 #### Prevent IE from Opening Untrusted HTML
 
        helmet.ieNoOpen()
  
 #### Ask Browsers to Access Your Site via HTTPS Only with method 
 
        helmet.hsts() [ Add configuration object {maxAge: timeInSeconds, force: true} ]
        
 #### Disable DNS Prefetching with method 
 
       helmet.dnsPrefetchControl()
     
 #### Disable Client-Side Caching with
 
       helmet.noCache()
       
 #### Set a Content Security Policy with 
 
      helmet.contentSecurityPolicy()
      app.use(helmet.contentSecurityPolicy({ directives: { defaultSrc: ["'self'"], scriptSrc: ["'self'", "trusted-cdn.com"] }} ))  [This can be added to your app.js file ]
