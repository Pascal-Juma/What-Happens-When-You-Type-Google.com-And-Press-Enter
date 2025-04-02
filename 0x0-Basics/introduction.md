# Introduction to what happens when you type Google.com and press Enter

### 1. Initial Typing

When you type 'Google.com' in your web browser address bar, the following happens:
- The first letter you start typing 'G' the browser will either start looking for your history and pages that start with letter 'G' in your recent visited history and start showing you an autocomplete list or some browser will actually do a search to an index that is local through this locally searched index that is cached. Some browser might actually send the request to a server to the default search engine baked into the browser.

### 2. URL Parsing

You finished typing 'Google.com' and about to hit enter, you didn't add any HTTP slash or anything else and now you hit enter. And now what the browser does it accepted that. Now you have 'google.com' as a string the browser will start parsing this thing and it asks a question is this a URL or is this a search term. If it's a search term it actually does a search and for this case it will not go through this route. If it's a URL it visits that page. 

It starts the process to visit 'google.com' page. We will now take this route, it figured out it's a page, a website so the browser will want to establish a connection with that website and it wants to send a get request to that website.