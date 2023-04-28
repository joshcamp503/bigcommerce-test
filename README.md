# bigcommerce-test
A light BigCommerce theme builder test...

STORE PREVIEW INFO

Preview URL: https://josh-campanella.mybigcommerce.com/?ctk=85cea0d1-f2bf-45e0-80d6-d4a4cca509fb
Preview Code: v38hxrzldh

TEST SUMMARY:

Hover Feature
  1) Open a script tag in responsive-img.html.
  2) Check to make sure the user has navigated to the Category page 
  3) Query the API for the product image urls.
  4) Add mouseover/out event listeners that chang the <img> src urls accordingly. 
  **Ideally I would have made this feature available for all products in all categories but I am admittedly unfamiliar with the Stencil framework and GraphQL.

Add All To Cart/Remove All Items
  1) Add the Add All To Cart button to category.html, open a script tag and bind that button to a const. 
  2) Query Storefront API for a cart.
  3) If a cart already exists, create and append the Remove All Items button to the DOM, if not then return the cart object.
  4) Get the product ID of the first item on the page
    **I actually create a list of the IDs of all the items on the page so that I could have the option to try and add all items to cart
  5) Use click event on Add to Cart button to create a cart with the first product on the category page and then append a Remove All Items button to the DOM
  6) Remove All Items button on click gets the cart ID from the API and uses it to delete the cart and then remove the Remove All Items button from the DOM

Display Banner if user is logged in
  1) When category.html loads, query the API for customer data
  2) If a customer exists send their data through to the displayUserBanner function
  3) Check for existence of addToCartButton to ensure user is on category page
  4) Create and style the user banner, inject customer data into it, then prepend it to the .navUser element

Final thoughts:

Writing the javascript to execute these tasks was simple enough. I found the documentation was sufficient to work through most things. The API structure was a little hard to figure out at first, but once I figured it out it was pretty simple. A pesky strict-origin-when-cross-origin issue with the local proxy server tripped me up, but I debugged it in my local dev environment. And finally, on the bonus task, I couldn't get a feel for exactly how to grab the data that Handlebars was injecting. I can see how it works but in the time I had I couldn't wrap my head around it enough to use it for the bonus task. I'm intrigued though and excited for the opportunity to work with Handlebars and the Stencil framework more. I'm most familiar with React and I like that Stencil is based on building modular components in a similar way.