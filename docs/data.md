# Understanding Our Data Files 📚

Hey there! Let's learn about how we store information in our zodiac app. It's actually pretty cool and simple once you understand it! 

## What is JSON? 📝

JSON (JavaScript Object Notation) is like organizing your school backpack, but for computer data! 

Imagine your backpack 🎒:
- You have different pockets for different things
- Each pocket might have a label (like "Books" or "Lunch")
- Inside each pocket, you have specific items

In JSON, we do the same thing with information:
```json
{
  "backpack": {
    "frontPocket": ["pencils", "eraser"],
    "mainPocket": ["math book", "lunch box"],
    "sidePocket": "water bottle"
  }
}
```

## Our Data Files 📂

### 1. clubs.json 👥
This json files contains a sample of clubs offerings of PSHS-MC that students could select to join
This JSON file will be used to populate <select>
   form elements to have only school endorsed clubs.
</select>
Example content is shown below:

```json
{
  "ACTS": "Acts isn't just a club. It's a community. Acts is the official non-denominational Christian organization of Pisay Main.",
  "Aksis": "Aksyon Iskolar, or AKSIS, is the official social action club of PSHS-MC. Our main goal is to promote, develop, and inspire social awareness and action in the student body of our school."
}
```

This file is not edited by students but by the admin of this website.

### 2. clubmembers.json ⭐
This json file is used to record student signup per club
Student can sign-up for several clubs

```json
{
  "students": [
    {
      "studentID": 12345,
      "fullName": "Aline Mendoza",
      "birthday": "2005-04-06",
      "email": "aline.mendoza@example.com",
      "mobile": "+63-912-345-6789",
      "gradeLevel": "Grade 12",
      "type": "intern",
      "preferredClub": "ACTS",
      "reason": "To foster meaningful connections and grow spiritually within a supportive community."
    },
    {
      "studentID": 67890,
      "fullName": "James Santos",
      "birthday": "2006-08-15",
      "email": "james.santos@example.com",
      "mobile": "+63-915-654-3210",
      "gradeLevel": "Grade 11",
      "type": "extern",
      "preferredClub": "Bake Club",
      "reason": "I want to learn baking techniques and share my creations with others."
    },
    {
      "studentID": 11223,
      "fullName": "Samantha Cruz",
      "birthday": "2007-02-20",
      "email": "samantha.cruz@example.com",
      "mobile": "+63-917-678-2345",
      "gradeLevel": "Grade 10",
      "type": "intern",
      "preferredClub": "Alianti",
      "reason": "To improve my skills in Ultimate Frisbee and participate in tournaments."
    }
  ]
}
```

Based on the structure of clubmember.json:
- There is only one main property **students**
- **students** property contains an array of students who signed-up for a club
- this JSON file will be read in the Club Member List (index.hbs) to show list of students who signed up for a club

## Why Use JSON? 🤔

1. **Easy to Read** 📖
   - Just like how you organize your notes with bullet points and sections
   - Both humans and computers can understand it easily!

2. **Easy to Update** ✏️
   - Adding new information is like adding a new page to your notebook
   - We can change information without messing up other parts

3. **Works Everywhere** 🌍
   - Like how everyone understands what a backpack is
   - JSON is a universal language that all computer programs understand

## How We Use It In Our App 🚀

1. In Club Member List **(index.hbs)**
   - All content of clubmembers.json will shown inside a table
   - clubs.json will be used under Filter by Club to control the list view inside the table of student sign-up

2. In Student Club Sign-up form **(joins.hbs)**
   - clubs.json will be used in a drop-down menu for student can select the club they would like to join/
   - clubmembers.json will be used to contain the student sign-up information.
   - for this application, the student can have multiple club sign-up
   
Remember: JSON is just a way to organize information neatly - like having different folders for different subjects in school. In this case it is used to keep track club sign-up. 🌟

## Fun Fact! 🎯
If you opened these files on your computer, they'd look like regular text files - but they're special because they're organized in a way that both you and the computer can understand easily. It's like having a secret code that everyone can read! 

Now you know how we keep track of all the zodiac information in our app! Pretty cool, right? 🎉
