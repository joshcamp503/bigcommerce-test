# bigcommerce-test
A light BigCommerce theme builder test...

STORE PREVIEW INFO

Preview URL: https://josh-campanella.mybigcommerce.com/
Preview Code: v38hxrzldh

TEST SUMMARY:

After submitting the link to the github repo on 4/28/2023, I made a few upgrades over the weekend. The updates are annotated below

Hover Feature
**UPDATE: 4/30/2023 - I retooled this feature to work for all images on every category page
  1) Open a script tag in responsive-img.html.
  2) Check to make sure the user has navigated to the Category page 
  **query the dom for a list of all product cards and images
  **for each product do the following:
  3) Query the API for the product image urls.
  4) Add mouseover/out event listeners that change the <img> src urls accordingly. 

Add All To Cart/Remove All Items
**UPDATE: 4/30/2023 - I retooled this feature to not jsut create a new cart, but to also add items to an existing cart if there is one
  1) Add the Add All To Cart button to category.html, open a script tag and bind that button to a const. 
  2) Query Storefront API for a cart.
  3) If a cart already exists, create and append the Remove All Items button to the DOM, if not then return the cart object.
  4) Get the product ID of the first item on the page
    **I actually create a list of the IDs of all the items on the page so that I could have the option to try and add all items to cart
  5) Use click event on Add to Cart button to create a new cart with the first product on the category page (or add the item to an existing cart), then append a Remove All Items button to the DOM, then notify user. (I opted to use an alert for this to keep it quick and easy, but this obviously the place to spin up a nice modal.)
  6) Remove All Items button on click gets the cart ID from the API and uses it to delete the cart and then remove the Remove All Items button from the DOM

Display Banner if user is logged in

**UPDATE: 4/29/2023 - I retooled this feature to utilize handlbars {{#if customer}} <nav><ul>list of customer data</ul></nav> and run a function to style this html

**PREVIOUS:
  1) When category.html loads, query the API for customer data
  2) If a customer exists send their data through to the displayUserBanner function
  3) Check for existence of addToCartButton to ensure user is on category page
  4) Create and style the user banner, inject customer data into it, then prepend it to the .navUser element

Final thoughts:

Writing the javascript to execute these tasks was pretty simple. The challenge was getting familiar quickly with Stencil, Handlebars, GraphQL, and the API structure. Fortunately the BigCommerce documentation was clear and easy to navigate. I did have to debug a pesky strict-origin-when-cross-origin issue with the local proxy server, but I made a change to my local dev environment that cleared it right up. All that being said, I'm intrigued though excited for the opportunity to work with Handlebars and the Stencil framework more. I'm most familiar with React and I like that Stencil is based on building modular components in a similar way.
