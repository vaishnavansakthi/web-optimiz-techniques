# How to Secure Your React.js Application

Reference Link: {https://www.freecodecamp.org/news/best-practices-for-security-of-your-react-js-application/}

{https://dev.to/codemaker2015/13-ways-to-secure-your-reactjs-application-11me}

React.js is a scalable open-source JavaScript library and is one of the most commonly used front-end frameworks out there today.

It's dynamic and is easy to get started with if you want to create interactive web applications with reusable components.

There are lots of reasons to use React.js in your application:

1. its flexibility – you can create complex applications without reloading the webpage
2. its simplicity – you can get a project up and running quickly and easily
3. its ease of use with other JS libraries
4. its customizability – there are many open-source components that can be integrated with your project.

React is convenient and fast, which can make it risk-prone and it's easy to forget about security concerns.

Though React has a smaller number of attack points than other frameworks, it is still not entirely secure. Since React is compatible with other open-source components and does not have strong default security settings, it becomes vulnerable to security slips.

Your React application will be useless without proper security features, so it's better to err on side of caution and tackle these security threats head-on.

# 1. Cross-Site Scripting (XSS)

Reference Link: {https://www.stackhawk.com/blog/react-xss-guide-examples-and-prevention/}

There are two types of cross-site scripting attacks:

## Reflected XSS 
It arises when an application takes some input from an HTTP request and embeds that input into the immediate response in an unsafe way.

## Stored XSS 
It stores malicious payload on the server and serves it to unsuspecting users. But there is also a third category - DOM-based XSS, sometimes referred to as Type-0 XSS.

# 2. Broken Authentication

Reference Link: {https://www.stackhawk.com/blog/react-broken-authentication-guide-examples-and-prevention/} 

progressive web app reference: {https://create-react-app.dev/docs/making-a-progressive-web-app/}

Checklist to Fix React PWAs(progressive web app) from Broken Authentication Vulnerability. The React applications should enforce password checks, whether the password is strong or weak. Also, adding criteria like eight characters (minimum) having uppercase, lowercase, numbers, and symbols can prevent users from such attacks.

# 3. SQL Injection

Reference Link: {https://www.stackhawk.com/blog/react-command-injection-examples-and-prevention/}

This vulnerability exposes the database of your application. An attacker injects harmful SQL code that allows them to edit data without permission.

The hacker can get access to all your app's data, create fake ids, and even control administrator privileges.

# 4. XML External Entity Attack (XXE)

Reference Link: {https://www.stackhawk.com/blog/react-xml-external-entities-guide-examples-and-prevention/}

An XXE attack is a type of attack targeted with XML parsers. This occurs when the external entity reference is processed with a weakly configured XML parser which may lead to the disclosure of confidential data.

# 5. Zip Slip

Reference Link: {https://github.com/snyk/zip-slip-vulnerability}

There's a very specific vulnerability in React applications known as "zip slip" which involves the exploitation of the feature that enables uploading zip files.

The attacker could unzip the uploaded files outside the assigned directory if the archive used to unpack the zip file is not secure and then they can gain access to the file.

#  6.Arbitrary Code Execution

Arbitrary code execution is an attacker’s ability to run any code of his choice on the target machine. An arbitrary code execution exploit is a program which is run by the attacker to exploit the target machine using the remote code execution method.

# Best Practices for React.js Security
1. Secure basic authentication of your React app
    1. Cookies protection
    2. Encryption(like email and mobile number)
    3. Hashing passwords
    4. Validating and filtering data
    5. Sessions
2. Make sure that the HTML code is resilient
    1. Disable HTML markups
    2. Use escape characters
    3. Utilize dangerouslySetInnerHTML and sanitize HTML
3. Use allowlist/blocklist and validation while URL parsing

4. Always use the principle of least privilege when allowing a connection to any database
5. Secure your React APIs

6. Implement a Web Application Firewall (WAF)
    1. Network-based firewall which is on the hardware level.
    2. Host-based firewall that is integrated into the software.
    3. Cloud-based WAF
7. Set up proper file management
8. Never serialize sensitive data
    You can either use the serialize-javascript NPM module that will escape the rendered JSON
    or use complex JSON formats that will avoid serialization.


# How can you secure React.js applications for optimal performance?

Reference Link: {https://www.linkedin.com/advice/1/how-can-you-secure-reactjs-applications-optimal-mhcof}

## 1. Use HTTPS and SSL
    Reference Link: {https://create-react-app.dev/docs/using-https-in-development/}
    1. HTTPS encrypts the data between your server and your client, preventing anyone
    from intercepting or tampering with it.
    2. SSL certificates verify the identity of your server and ensure that your users are
    connecting to the right domain
## 2. Sanitize user input and output
    You can use libraries like DOMPurify or sanitize-html to help you with this task.
## 3. Implement authentication and authorization
    1. You should implement authentication and authorization using secure methods and
    protocols, such as JSON Web Tokens (JWT) or OAuth.
    2. You should also store your credentials and tokens in a safe place, such as local
    storage or cookies with the HttpOnly and Secure flags.
    3. You can use libraries like Auth0 or Firebase to simplify this process.
## 4. Optimize your code and bundles
    1. Hooks are also recommended over lifecycle methods.
    2. Code splitting and lazy loading can reduce the size of your initial bundle by only
    loading the necessary code for each route.
    3. Performance tools such as React DevTools or Lighthouse can be used to measure and
    enhance the quality and speed of your code.
## 5. Update your dependencies and audit your packages
    1. Regularly updating your dependencies and auditing your packages is a great way to
    secure your React.js applications and improve their performance.
    2. Dependencies are libraries or modules that you use in your application, such as
    React, React Router, or Axios, while packages are the files or folders that contain
    your dependencies, such as node_modules or package.json.
    3. Tools like npm or yarn make updating and auditing your packages easy



