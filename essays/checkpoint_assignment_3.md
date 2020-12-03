---
layout: essay
type: essay
title: Checkpoint Assignment #3
# All dates must be YYYY-MM-DD format!
date: 2020-12-03
labels:
  - programming
  - javascript
  - server
  - web development
  - checkpoint
---


Checkpoint A:

Describe your design for your site's shopping cart. That is, will it be a separate page that the user can view and edit, or will it be integrated into the product pages? If so, describe in detail how this will work on your site. Provide several examples of using the cart.


 My shopping cart will be available to the logged-in user via a modal pop-up, available at all times via a sticky shopping cart button in the lower right corner of the screen. The number of items currently in the cart will be shown on the button with a number badge (like a mobile app with unopened notifications). It will look very similar to the final invoice but will feature plus and minus buttons next to the quantity number that can be changed or removed from the cart. The subtotal and tax and shipping is calculated in as the user updates the cart. The cart will feature a 'checkout' button at the bottom which will take the user to a final order confirmation page to confirm their shipping address, payment method, and email before finally ordering.
 

Checkpoint B:

Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their keys) you will use to manage the shopping cart data and how they will beused in $_SESSION.


 Sessions will be used to track session IDs of each user on the site. When the user logs in, this session ID is matched to a user in the user data file (JSON) and a copy of the whole user object plus their session ID is stored to a global object of on the server which stores all currently logged-in users (an object of objects). This global object will not only track current users, but also be used as server-side storage for any data for the user (including shopping cart contents). Cookies with expiration dates will store this data on the client side and if the client checks out or updates quantities in their cart, the object is updated on the request and cookies updated on the response. 

 

Checkpoint C:

How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?


 Any user can view the product pages, even when not logged in, but only purchases can only be made by registered, logged in users. Since my server is constantly tracking and matching session IDs to currently logged in users using the global object, if a valid POST request is made to try to checkout by an user with a session ID that is not paired to a user, the server will respond with a login screen telling the user to login/register to proceed to checkout. Their order is also stored in the global object with their session ID on the server as well as on the client via cookies. I don't want to fully trust just the user's cookies, since they can be edited by the user, so when the user finally logs in, the order cookie is checked to match the original copy we stored on the server. These must match to proceed to check out. 

The passwords of the users are also stored in my user data file (JSON) in plain text. This should be encrypted to protect the users and if I have time, I might implement a simple encryption of the passwords.

 

Checkpoint D:

Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary):

When the user logs in, a persistent 'Welcome, youname' message appears in the top right corner, relacing a 'Login' button. The user's name is also used at checkout thanking them for their purchase.

 

Checkpoint E:

If you are working with partners, how will you split up the work in your team so that you are working in parallel as effectively as possible? That is, who is doing what and when?


I am not working with partners.
 

Checkpoint F:

How are you approching Assigment 3 differently than Assignment 2?

With assignment 2, I mostly added new features incrementally on top of Assignment 1. The fundamental design of this site is so different for Assigment 3 that I am rewriting or refactoring nearly all my code from the ground up. I'm designing the whole thing first in Adobe UX to make sure what's in my head makes sense and feels right. Then I'm drawing out diagrams to make clear in my head where all the data is flowing in each case, since my server is getting very complex (at this point, nearly 700 lines of code). I may use Express routers to keep my server.js file clean and offload some functions to separate files to keep things modular and small.
