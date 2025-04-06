# Requirements 🌟

- This is the 2nd Phase of the web application that we started in the 3rd qtr 4th-graded exercise.

- The 3rd Qtr 4th-graded exercise, was designing a club sign-up form.

- In this non-graded exercise we are initially shown a club member list through loading index.hbs.

- In this club member list, all students who signed-up for a club are displayed.

- Then user can filter the students' list per club sign-up.

- When a user clicks on the button **Click Here to Join a Club**, the sign-up form
which we initially designed in the 3rd Qtr will be displayed.

- You are now tasked to complete this application of saving the students' club sign-up to a club.

- Refer to the other .md files inside the docs folder, for more details regarding this app.

## What you need to do? 🚀

1. Edit server.js to include the necessary routes for **/join** using app.get and for **/submit-form** using app.post.
2. In the /join route, render or open join.hbs and pass **clubArray** variable 
3. Inside join.hbs, using appropriate handlebars, complete the select list below to contain
   club name - club description options, using club names as the option value.
  ```html
    <select id="preferredClub" name="preferredClub" required>
               <!-- use handlebars to create a drop-down of clubs' name -->
    </select>
   ```
4. In the /submit-form route, create a routine to save the entered data and then redirect to /join.
5. Successful implementation, means that when user clicks on **Click Here to see Member List**, 
   the sign-up information should show on the list. 

**Remember:** This is a real web application that you can interact with - just like the big websites you use every day! The main difference is that we've made it simple. 🌟
