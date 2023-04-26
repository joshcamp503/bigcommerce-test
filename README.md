# bigcommerce-test
A light BigCommerce theme builder test...

These are the steps I took to complete this task:

Created a BigCommerce trial store on the BigCommerce webpage.
Created an empty github repo, cloned it to my computer, and found the BigCommerce developer documentation. 
Installed Stencil CLI according to the docs, then downloaded the Cornerstone theme .zip from the store dashboard.
Extracted the .zip contents to the root folder of my git repo.
Followed the docs to procure a store API key and initialize the store locally using stencil init.
Added a new product category and a new product to my store using the store dashboard, images included.
HOVER FEATURE:
I used the BigCommerce docs to find the API endpoint for the "Special Item" product images.
From here I was able to see all the BigCommerce CDN URLs for the images.
At the bottom of responsive-img.html I added a script to target the image in the DOM and change it's src and srcset attributes upon mouseover and mouseout.
I was happy to see that the image maintained it's responsiveness as well.

