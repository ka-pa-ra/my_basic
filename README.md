# My Basic
 My Basic was created for educational purposes, it's my 4rd **Milestone** **Project** 
 which complete my Full Stack Frameworks with Django Milestone Project.
 
 A live **desktop demo** you can find [here](https://mybasic1.herokuapp.com/).
 
 The **source code** you can find [here](https://github.com/ka-pa-ra/my_basic).

# UX
My Basic is a online clothes shop.  

The website offers to users the action of buying clothes, selecting clothes, and arranging for its delivery. And also to pay for the products 
with a credit or debit card. 

## Project Goals:

### Target Audience

* People who wants buy clothes.

### Visitor/user goals:

* Purchase products shown on the website in a safe and secure way
* Get information about the products

### Business goals:

* Provide users with a secure professional e-commerce online shop
* Make profit from selling clothes 
* Promote own Brand, make the brand more recognisable and expand the business

# User Stories

## User Story One:
As a user, I expect to access the website from any device, so that I can use the website anytime and anywhere.

## User Story Two:
As a user, I expect to easily navigate the website, so that I can quickly find what I'm looking for.

## User Story Three:
As a user, I want to view service details and product details (e.g. image, price, description), so that I can book/buy some of them.

## User Story Four:
As a user, I want to search and filter the products easily, so that I can quickly find a specific product I am looking for.

## User Story Five:
As a user, I want to view and modify my order in the cart before completing it, so that I can make last changes easily before proceeding to payment.

## User Story Six:
As a user, I want to view a total price of my purchases and delivery cost, so that I will understand and see how much I will be charged.

## User Story Seven:
As a user, I expect to make payments by card in a safe and secure way, so that I won't be concerned about the safety of my card details and won't be charged incorrectly.

## User Story Eight:
As a user, I want to receive an email confirmation after checkout, so that I can make sure that payment was successfull.

## User Story Nine:
As a user, I want to create my own account, so that I can save, view and edit my profile details and view my order history.

## User Story Ten:
As a user, I want to easily login anytime, so that I can get access to my saved profile details and make next purchase quicker.

## User Story Eleven:
As a user, I want to be able to change my email or add the second email, so that I can have an easier access to the website's functionality and to gain more flexibility.

# AdminUser Stories

## AdminUser Story One:
As a AdminUser, I want to have convenient and secure admin interface avalable only for website admin, so that I can add, edit and remove products/services.

## AdminUser Story Two:
As a user, I want to receive emails from the users when they fill out the contact form, so that I can reply on them satisfying users queries.

# Design 
## Frameworks 

* [Bootstrap](https://getbootstrap.com/), front-end framework is chosen for this project for its modern interface, ease of use and ability to be easily customized.
  It is used for creating features such as navbar, cards, forms, modals, as well as for the layout.

* [JQuery](https://jquery.com/) is used for initializing some Bootstrap components, as well as for custom functions, DOM manipulation.

# Features

### Navbar 
The navbar is fixed at the top of the page all the time, this allows a user to easily navigate throughout the website. My Basic is located in the top left corner on a desktop, it redirects a user to the home page when clicked. On smaller resolutions (tablet, mobile) the navbar is collapsed into a toggler icon. Menu links appear when the toggler icon is clicked and collapse back, when clicked again.
Navbar also contains a search box (center), where a user can search for products. It is collapsed into a search icon on the mobile and tablet, and slides down when the icon is clicked.
Also, navbar contains a shopping bag icon along with a grand total displayed if there are items in the shopping bag added. It changes the colour  when there's something in the shopping bag to catch user's attention, and remains white (as other navbar elements) when the shopping bag is empty. Clicking the shopping bag icon redirects a user to the shopping bag page.
For non-logged in users or guests navbar contains the following links: Login, Register.
For logged in users it contains the _My Account_ nav-item which toggles down the following links that redirect user to the corresponding pages: _My Profile_, _Logout_.
* For admin apart from all the links available for logged-in users, there is also a link to the Product Management page, where admin can add new products and services. This is avaliable only for superusers.
  Defensive design with corresponding error messages is in place to protect this page from manual entering the url in the browser.

### Homepage 
Hero image section contains a full-screen image, main heading with 1 button _Buy Now_ which redirect a user to products pages.
The purpose of this section is to attract new users, to make the first impression and to call to action.

### Product Page

* The "All products" page displays product cards, including the following information: category, name, price. All product cards are clickable and redirect a user to the individual product page with detailed information.
* Clicking on Add to bag button will add the product to the shopping bag with quantity equal to 1, clicking again will simply updates the quantity by 1. This functionality was added to enhance user experience, to allow users straight away add an item to the shopping bag without viewing products details and giving more flexibility to use the website.
* If the user is admin, there are also 2 buttons displayed in the cards: Edit and Delete. Clicking Edit button redirects admin to the Edit Product page. Delete button toggles the Delete modal. It asks a superuser to confirm if the product is to be deleted. If so, upon clicking "Delete" button, the product will not be removed from the database, but will set as discontinued and will be removed from the user's view. 
  Then the page reloads and the toast-message will inform about the sucessfull deletion. 
  There is also a button "Cancel" that closes the modal when it's clicked. 
  These actions can be done only by superuser, attempts to access them by other users will end up with redirection to the landing page with toast error messages displayed.
* User can filter the products by category to see the specific items. When the category is clicked, only products of the selected category are displayed, as well as the Category Name and a number of the items satisfying the query.

### Product details page

* The product details page displays information about the selected product: category, name, description, rating, price and product image (or placeholder if no image was added). Clicking the image will open it in the new tab, if the image_url is assigned.
* The item quantity can be assigned filling the quantity form, the validation is in place restricting the quantity to the range of 1-999. The validation errors will be displayed, if the user tries to input the numbers outside of that range.
* Product can be added to the bag by clicking Add to bag button, that will be reflected in the shopping bag icon in the navbar (grand total will be increased there). As well as that, the toast success message will be displayed when the product is added to the bag.
* also contains a form where user can choose sizes.
* If the user is admin, there are also 2 buttons displayed below the product name: Edit and Delete. Clicking Edit button redirects admin to the Edit Product page. Delete button toggles the Delete modal. It asks a superuser to confirm if the product is to be deleted. If so, upon clicking "Delete" button, the product will not be removed from the database, but will set as discontinued and will be removed from the user's view. Then the page reloads and the toast-message will inform about the successfull deletion. There is also a button "Cancel" that closes the modal when it's clicked. These actions can be done only by a superuser, attempts to access them by other users will end up with redirection to the landing page with toast error messages displayed.

###  Shopping Page

* Shopping page is available for both logged in and non-logged in users, so that it is possible to make purchase being a guest.
* The page contains a summary of the user's order: the item's name, image, descriptions, size, quantity, price, sub-total and sku(for products).
* A user can update item's quantity and remove items from their order completely. To prevent from the accidental clicking the remove button, the modal will be opened on click asking a user to confirm the deletion. If a user tries to enter invalid quantity, error message will be displayed when "Update" button is clicked and will prevent the invalid form submission. The error message will inform about the possible range: 1-999 for product's quantity and 1-100 for service's number of participants fields.
* Toast messages will be displayed when a user updates/removes items in the cart.
* At the bottom of the page the bag subtotal, delivery cost and grand total are displayed.
* There is a _Checkout_ button that takes a user to the checkout page to proceed with the payment.
* There is _Keep Shopping_ button that takes a user back to all products page.

### Checkout Page 

* Order summary includes short information about items in the order (image, name, quantity, subtotal), the link to _Adjust Bag_ ( that redirects a user to the Shopping page), delivery cost and also Total to pay.
* Checkout form sections are the following: Personal Details, Billing/Shipping info and Payment.
* The validation messages will be displayed on click _Complete Order_  button, so a user can move on the next tab only if the current form-section is filled with valid information.
* The save info checkbox allows the form information to be saved to the user's profile for the logged in users.
* If it's a new or non-logged user there are links to register or login pages, in case a user wants to save the information to their profile.
* Before proceeding the payment, user can review and check all the information in the table (Form Summary).
* A user is informed how much the card will be charged in the paragraph below the Proceed to payment button.
* Since the website is made for educational purposes only and the Stripe functionality is only for testing, only 4242 4242 4242 4242 card number will lead to the successfull payment. A user is asked to provide card number, expiration date (any date in future) and CVC (any numbers).
* A webhook is used to make sure that the order is processed even in the cases when the payment process is interrupted (e.g. if a user accidentally closes the page or browser after clicking "Proceed to payment" button).
* Once the form is submitted and the payment is successfully proceeded, the Checkout success page is loaded and a confirmation email is sent to the user's email. Also, a toast message appears to ensure the user that the order was processed successfully.

### Checkout Success page

* The paragraph with a Thank you message is displayed on the top of the page to inform a user that the payment was processed and the email was sent to the user's email.
* The 3 sections Order info, Shipping details and Order Summary contain all the information about the completed order.
* Keep shopping button redirects user to the Products page.
* For logged-in users there's a button View full order history that takes users to the order history page.

### Profile page

Profle feature is available only for authenticated users.

* Profile page contains Personal info section (username and email displayed). Also it contains 2 buttons Change password and Manage emails (changing the current or adding a new email) that take a user to the corresponding pages (that's a part of Django allauth functionality with a customized templates).
* Shipping details section allows to save the shipping information, so for the next purchase the fields in the checkout form will be pre-filled with this info. User can update this information anytime.
* View order history link will redirect a user to the Order History page.

### Order history feature is available only for authenticated users.

* If a user has not made any purchases, the paragraph will inform that the order history is empty with a link to the Product page.
* If there are completed orders, the table with the following fields: Order Number, Date, Items, Total is in place.
* Clicking the link on the Order number will redirect a user to the checkout success page with all the order information. The Toast info message will tell the user that it's a past confirmation for the order number.
* My Profile link will redirect a user to the Profile page.

### Admin product managment
Product managment feature is available only for authenticated superuser. Admin page allows an owner of the website to add new products/services by filling out one of the two forms - Add New Product and Add New Service on the Product Management page. If the form is valid, the product/service is added to the database and the user is redirected to the new created product/service details page. The defensive design is implemented to restrict other than admin users to manually enter the url to get access to the page. User will be redirected to the home page with the toast error messages appeared. Edit and Delete product/service functionality allow an admin to make the corresponding manipulations. The Delete functionality was updated during the development, so the product/service is not being completely removed from the database, but set as discontinued and is hidden from the user's view and can be set as active again any time.

### Django-allauth features
#### Sign Up
The sign up page allows a user to create a new account. The user is asked to fill the fields "email", "username", "password" and "password (again)". When adding a username, the code compares it against existing email to ensure that it is unique. If user's input does not meet requirements, flash messages will inform a user about the error. When the form is submitted, a verification email is sent to the user's email to verify the email and finish registration process.
There is also a link to the login page for existing users at the bottom of the form.
The Registration page is only available to anonymous users and logged-in users are redirected out automatically.

#### Login
The login page features the form with "username" and "password" fields, allowing registered users to log into their account. If the login was successfull, a user is redirected to the home page and the toast success message appears informing that the log in was successful. Otherwise, flash messages will be displayed about incorrect user's input.
There is also a link to the sign up page for new users at the bottom of the form. As well as that, there's a link to the forgot password functionality, using which a user can reset their password. The login page is only available to anonymous users and logged-in users are redirected out automatically.

#### Logout
Hitting "logout" button renders logout page, asking to confirm if a user wants to logout. It will end their session and redirects to the homepage with a toast success message appeared.

#### 404 and 500 error pages
Custom 404 and 500 pages contain heading, short information about the error and a button "Back Home". As well as that, they display navbar that allows users to come back easily to any page if they got lost.

# Technologies Used

## Languages
* HTML
* CSS
* JavaScript
* Python
* Jinja - templating language for Python, to display back-end data in HTML.

## Libraries and Frameworks 

* Django - Python framework for building the project.
* Bootstrap - as the front-end framework for layout and design.
* Google Fonts - to import fonts.
* FontAwesome - to provide icons used across the project.
* JQuery - to simplify DOM manipulation and to initialize Bootstrap functions.
* Gunicorn - a Python WSGI HTTP Server to enable deployment to Heroku.
* Psycopg2 - to enable the PostgreSQL database to function with Django.
* Stripe - to handle financial transactions.
* Django Crispy Forms - to style Django forms.

## Tools 

* GitPod - an online IDE for developing this project.
* Git - for version control.
* GitHub - for remotely storing project's code.
* PIP - for installation of necessary tools.
* Heroku - to host the project.
* AWS S3 Bucket - to store static and media files in prodcution.
* Boto3 for compatibility with AWS.

## Databases

* SQlite3 - a development database.
* PostgreSQL - a production database.

# Deployment in GitHub

1. On GitHub, navigate to your site's repository.
2. Under your repository name, click Settings.
3. Under "GitHub Pages", use the None or Branch drop-down menu and select a publishing source.
4. Optionally, use the drop-down menu to select a folder for your publishing source.
5. Click Save.

[A live project page.](https://ka-pa-ra.github.io/my_basic/)

# Deployment to Heroku

1. Create a requirements.txt file by typing pip3 freeze --local > requirements.txt into the terminal line.

2. Create a Procfile by typing echo web: gunicorn my_basic.wsgi:application

3. Add, commit and push these changes to Github.

4. Navigate to the Heroku.

5. Create new app and give it a unique name.

6. Choose the region that is closest to you.

7. Go to the Deploy tab and choose Github.

8. Search for the correct repository and connect.

9. Go to Heroku Settings and navigate to Config Vars.

# Credits
* The following site has been used as an inspiration for  [My Basic](https://mybasic.it/)

* The code for the navigation bar, forms and views was duplicated from Code Institute's Full Stack Frameworks with Django Milestone Project.

* Bootstrap - for providing documentation on the framework.

* W3schools - for various code segments, examples and explanations used throughout the project.

* Font Awesome - CDN for icons used in the project.

* Google Fonts - CDN for fonts used in the project.

* Images take using [My Basic](https://mybasic.it/) and [Unsplash](https://unsplash.com/).
