# Introduction to what happens when you type Google.com and press Enter

### 1. Initial Typing

When you type 'Google.com' in your web browser address bar, the following happens:
- The first letter you start typing 'G' the browser will either start looking for your history and pages that start with letter 'G' in your recent visited history and start showing you an autocomplete list or some browser will actually do a search to an index that is local through this locally searched index that is cached. Some browser might actually send the request to a server to the default search engine baked into the browser.

### 2. URL Parsing

You finished typing 'Google.com' and about to hit enter, you didn't add any HTTP slash or anything else and now you hit enter. 

And now what the browser does it accepted that. Now you have 'google.com' as a string the browser will start parsing this thing and it asks a question is this a URL or is this a search term.

 If it's a search term it actually does a search and for this case it will not go through this route. If it's a URL it visits that page. 

It starts the process to visit 'google.com' page. We will now take this route, it figured out it's a page, a website so the browser will want to establish a connection with that website and it wants to send a get request to that website.

### 3. Find Protocol

The next step is determining which protocol and which port to connect to.The browser needs to also know if its either HTTP or HTTPS.

Is it HTTP unencrypted Port 80 or is it HTTPS encrypted on Port 443. By default, prior to certain version browsers were always going to HTTP.

But then the browser invented concepts called HTTP Strict Transport Security which essentially is a list that the browsers keep cached in its local database. 

So what the client does is it looks through this list and checks if 'Google.com' an HTTPS site or is just a normal HTTP. If found in the HSTS list then it uses the HTTP protocol that means that the Port will be 443. And if it's not in the list then it will be forced to use HTTP.

Now that the browser went through the HTTPS part which is Port 443 and it's secure so now it will establish a secure connection to the 'Google.com'

### 4. DNS lookup

DNS stands for Domain Name System. After knowing the Protocol the browser needs to know also the IP Address to communicate with 'Google.com'.

And to get that the client asks a DNS query and here are the layers of the DNS query. 
- The first thing the client will check if it has an IP address for 'Google.com' its own cache.
- When it doesn't find it in the cache, it will ask the operating system if it has an IP Address of 'Google.com' in the host file.
- If it doesn't find it and the browser supports DOH which is DNS over HTTPS it will see what is the default HTTPS DNS provider and establish a TLS connection.

### 5. TCP Connection

To establish the TCP connection we need to know the IP Address(for this case will be 4.1.2.3), destination of the request, which Port we are going to use (443), my internal IP Address(10.0.0.1), my random port (2222).

Since 4.1.2.3 is not in my subnet so i will the request through the gateway which is (10.0.0.1) and gateway changes the IP Address to public one as (4.1.2.4) and sends it over.

And assuming that a three way handshake happened, we now have a full connection between a client and 'Google.com' and we now have TCP connection.

### 6. TLS, ALPN, SNI

TLS stands for Transfer Layer Security. To do the client hello, that first request after the TCP connection, we are going to establish a public key and a private key in my client and merge them. 

