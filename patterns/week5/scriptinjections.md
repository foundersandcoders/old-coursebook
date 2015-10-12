#Script Injections
####What they are and some examples
Attacks work by injecting code, usually a client-side script such as JavaScript, into a Web application's output. 
Most websites have numerous injection points, such as search fields, feedback forms, cookies and forums 
that are vulnerable to cross-site scripting. The most common purpose of XSS attacks (aka script injections) is to gather cookie data, 
as cookies are commonly and regularly used incorrectly to store information such as session IDs, user preferences 
or login information. Although client-side scripts cannot directly affect server-side information, 
they can still compromise a site's security, often using Document Object Model manipulation to alter form values or 
switch the form action to post the submitted data to the attacker's site.

This type of attack is possible by the way the client browser has the ability to interpret scripts embedded within 
HTML content enabled by default, so if an attacker embeds script tags such `<SCRIPT>, <OBJECT>, <APPLET>, or <EMBED>`
into a web site, 
the web browser's JavaScript engine will execute it. 
Typical targets of this type of injection are forums, guestbooks, or whatever section where the administrator 
allows the insertion of text comments; if the design of the web site isn't parsing the comments inserted, 
and takes '<' or '>' as real chars, a malicious user could type:

`I like this site because <script>alert('Injected!');</script> teaches me a lot`

If it works and you can see the message box, the door is opened to the attacker's imagination limits!

Some other examples of attacks exploiting XSS vulnerabilities are, stealing data, taking control of a user's session,
running malicious code, or being used as part of a phishing scam.

####How to prevent these types of attacks
Explanation of some common approaches to this problem: 

http://www.computerweekly.com/tip/Cross-site-scripting-explained-How-to-prevent-XSS-attacks

Npm module designed to prevent xss attacks: 

https://www.npmjs.com/package/xss




