# Burgers-to-Eat
A burger logger created with MySQL, Node.js, Express, and Handlebars.

### Visit

You can visit the deployed site at the following URL: https://thawing-ocean-73628.herokuapp.com

### Overview

This burger logger allows the user to add list items to a menu of burgers and to "eat" a chosen burger (i.e., to move a burger from the menu to another column representing burgers eaten) by clicking a button. The user can also "throw away" (i.e., delete) burgers from either column. Because the burger data is stored in a database, the status of each burger is the same for all users and persists over time: if one user adds, deletes, or eats a burger, then this update will be reflected to all users who visit the site and will remain after the user reloads the page.

### Technical Approach

* The app uses *ORM* (object-relational mapping) to handle the CRUD (create, read, update, and delete) functions of adding, displaying, eating, and throwing away burgers. Queries to the database make use of SQL.
* The architecture follows the *MVC* (model-view-controller) structure:
    - The *model* (i.e., the "burger.js" file) makes use of the "orm.js" file in the "config" folder to give each burger the CRUD functions described above, using the database to record user input.
    - The *views* (i.e., the Handlebars files) determine the user interface and make the UI selectively display information according to the data stored in the database (e.g., which burgers have been added but not yet eaten, eaten but not yet deleted, etc.).
    - The *controller* (i.e., the "burgers_controller.js" file) establishes the routes and mediates between the model and the views by interpreting each user input as a request that triggers one of the model's CRUD functions and updates the views (and, thereby, the UI) accordingly.
* The server is powered by Node.js and Express.

### User Guide

* To *add* a new burger, type the name of the burger in the "Burger Name" field in the "Add a Burger" section. Then, click the "ADD" button. For 1.5 seconds, you will be shown a GIF related to the creation or appreciation of burgers.
* To *eat* a specific burger from the menu displaying "Some Tasty-Looking Burgers," click the "BURGER TIME" button next to the desired burger. For 5 seconds, you will be shown a GIF related to the joy of eating a burger.
* To *delete* a specific burger from either the menu or the "Burgers Devoured" column, click the trash can symbol next to the burger you wish to throw away.
