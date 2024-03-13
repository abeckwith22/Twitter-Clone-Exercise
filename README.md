# Twitter-Clone Warbler Exercise

- [ ] Create the virtual environment
- [ ] Set up the database

#### Part 1: Fix Current Features
- [x] **Step 1: Understand the current model**
    - [x] Read *models.py*. Make a diagram of the four tables.
    - [x] Note that the *follows* table has an unusual arrangement: it has two foreign keys to the same table. Why?
    - [x] Using pdb, set a debugger in one of your routes, and hit it to pause code execution. From here, try out the various relationships set on the model classes. Get a feel for how they work.
- [x] **Step 2: Fix logout**
    Right now, there are links in the site to logout, but the logout route is not implemented. On logout, it should flash a success message and redirect to the login page.
- [ ] **Step 3: Fix User Profile**
    - [ ] The profile page for user works, but is missing a few things:
        - [ ] the location
        - [ ] the bio
        - [ ] the header image (which should be a background at the top)
- [ ] **Step 4: Fix User Cards**
    - [ ] On the followers, following, and list-users pages, the user cards need to show the bio for the users. Add this.
- [ ] **Step 5: Profile Edit**
    There are buttons throughout the site for editing your profie, but this is unimplemented.
    - [ ] It should ensure a user is logged on (you can see how this is done in other routes)
    - [ ] It should show a form with the following:
        - [ ] username
        - [ ] email
        - [ ] image_url
        - [ ] header_image_url
        - [ ] bio
        - [ ] password *[see below]*
    - [ ] It should check that that password is the valid password for the user -- if not, it should flash an error and return to the homepage.
    - [ ] It should edit the user for all of these fields *except* password (i.e. this is not an area where users can change their passwords-the password is only for checking if it is the current correct password.)
    - [ ] On success, it should redirect to the user detail page.
- [ ] **Step Six: Fix Homepage**
    The homepage for logged-in-users should show the last 100 warbles **only from the users that the logged-in user is following, and that user**, rather than warbles from *all* users.
- [ ] **Step Seven: Research and Understand Login Strategy**
    Look over the code in *app.py* related to authentication.
    - [ ] How is the logged in user being kept track of?
    - [ ] What is Flask's ***g*** object?
    - [ ] What is the purpose of ***add_user_to_g***?
    - [ ] What does ***@app.before_request*** mean?
