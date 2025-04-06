# Understanding Our Club SignUp Web App 🌟

Hey there! Let's explore how our Club sign-up web app works. We'll break down the main file (server.js) into easy-to-understand parts.

## 1. Getting Started 🚀

```javascript
const express = require('express');
const path = require('path');
const fs = require('fs');
```

Think of this part like packing your backpack for school. We're grabbing three important tools:
- `express`: This is like our web app's brain - it helps us create a website
- `path`: This helps us find files on our computer, like a digital map
- `fs`: This lets us read and write files (like saving your zodiac info!)

## 2. Setting Up Our Web App 🛠️

```javascript
const app = express();
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
app.use(express.static('public'));
```

This is like setting up a lemonade stand:
- We create our app (like setting up the stand)
- We tell it how to understand information from users (like having a menu)
- We set up a public folder for things everyone can see (like putting up signs)

## 3. Working with Files 📁

```javascript
const usersFilePath = path.join(__dirname, 'data', 'clubmembers.json');
if (!fs.existsSync(path.join(__dirname, 'data'))) {
  console.log('Creating data directory...');
  fs.mkdirSync(path.join(__dirname, 'data'));
}
```

This is like creating a filing system:
- We make sure we have a special folder called 'data'
- If it doesn't exist, we create it
- This is where we'll store everyone's zodiac information

## 4. Handling Web Pages 🌐

```javascript
// to show Club Member List
app.get('/', (req, res) => {
  try {
    const clubMembers = JSON.parse(fs.readFileSync(usersFilePath));
    const clubM = clubMembers.students; // Convert to array for easier template handling
    console.log('Users loaded:', clubM);
    // console.log("userList is", userList);
     res.render('index.hbs', {clubArray, clubM});
  } catch (error) {
    console.error('Error reading users file:', error);
    res.status(500).send('Error loading user data');
  }
});

// to show Student Club Sign-up Form


app.get('/join', (req, res) => {
  
});
```

Think of this like having different rooms in your house:
- When someone visits the main page ('/'), we show them the home page
- When they go to '/join', we go to the Club Sign-up Form

## 5. Processing Form Submissions ✍️

```javascript
app.post('/submit-form', (req, res) => {
  const signUPForm = req.body;
  // routine to save the student signup
  // then redirect to /join
});
```

This is like receiving a letter:
- When someone fills out the form and submit it, it will be saved inside clubmembers.json.
- then the form will be displayed again, until the link "Show Club Member List"


## 7. Starting the Web Server 🌍

```javascript
app.listen(3000, '0.0.0.0', () => {
  console.log(`Server is running on port 3000`);
});
```

This is like opening our lemonade stand for business:
- We tell our app to start running
- It listens for visitors on port 3000
- When it's ready, it lets us know it's running!

## Cool Things to Note 🌈

- The app saves students's information, so you can keep track who signed-up for which club.
- It assign students to the selected club.

**Remember:** This is a real web application that you can interact with - just like the big websites you use every day! The main difference is that we've made it simple. 🌟
