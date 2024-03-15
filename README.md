# Twitter-Clone Warbler Exercise

- [x] Create the virtual environment
- [x] Set up the database

#### Part 1: Fix Current Features
- [x] **Step 1: Understand the current model**
    - [x] Read *models.py*. Make a diagram of the four tables.
    - [x] Note that the *follows* table has an unusual arrangement: it has two foreign keys to the same table. Why?
    - [x] Using pdb, set a debugger in one of your routes, and hit it to pause code execution. From here, try out the various relationships set on the model classes. Get a feel for how they work.
- [x] **Step 2: Fix logout**
    Right now, there are links in the site to logout, but the logout route is not implemented. On logout, it should flash a success message and redirect to the login page.
- [x] **Step 3: Fix User Profile**
    - [x] The profile page for user works, but is missing a few things:
        - [x] the location
        - [x] the bio
        - [x] the header image (which should be a background at the top)
- [x] **Step 4: Fix User Cards**
    - [x] On the followers, following, and list-users pages, the user cards need to show the bio for the users. Add this.
- [x] **Step 5: Profile Edit**
    There are buttons throughout the site for editing your profie, but this is unimplemented.
    - [x] It should ensure a user is logged on (you can see how this is done in other routes)
    - [x] It should show a form with the following:
        - [x] username
        - [x] email
        - [x] image_url
        - [x] header_image_url
        - [x] bio
        - [x] password *[see below]*
    - [x] It should check that that password is the valid password for the user -- if not, it should flash an error and return to the homepage.
    - [x] It should edit the user for all of these fields *except* password (i.e. this is not an area where users can change their passwords-the password is only for checking if it is the current correct password.)
    - [x] On success, it should redirect to the user detail page.
- [x] **Step Six: Fix Homepage**
    - [x] The homepage for logged-in-users should show the last 100 warbles **only from the users that the logged-in user is following, and that user**, rather than warbles from *all* users.
- [x] **Step Seven: Research and Understand Login Strategy**
    Look over the code in *app.py* related to authentication.
    - [x] How is the logged in user being kept track of?
        The user is being kept track of using flasks *g* object.
    - [x] What is Flask's ***g*** object?
        Flask's ***g*** object is a global namespace that allows you to hold any type of data that could be relevant to your apps context. For this instance this would be the current user object that is logged in.
    - [x] What is the purpose of ***add_user_to_g***?
        The purpose of ***add_user_to_g*** is to make it so that the current user that is logged in can be accessible through ***g*** which makes writing code for user doesn't have to start off with a query everytime I need access to the current user in the db.
    - [x] What does ***@app.before_request*** mean?
        ***@app.before_request*** runs before every request to another site on that webpage. For this instance it's used to check and see if the user is still logged in after each page and if not then the user is redirected to `/`
