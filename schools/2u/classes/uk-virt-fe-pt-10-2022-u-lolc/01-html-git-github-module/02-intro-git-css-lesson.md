# 02-intro-git-css-lesson

lesson plan open tab

https://docs.google.com/presentation/d/1hVJs78yCTbNQugsd6kTJCWXrtSQmR9dBkxrANdnXwuY/edit

## Instructor - stoke curiosity - 10 min
slides

talk about pace
where to get help
objectives
talk about target learning path

what is git?
linus - https://www.youtube.com/watch?v=4XpnKHJAok8


git - very basic intro - makes it easier to collaborate with group

# Students - 10min
explain what git version control is for

# instructor - 10 min
github

```
GitHub offers a centralized location where all developers can push and pull (upload and download) their code. This means that GitHub always holds the most up-to-date code, handling everyone's updates appropriately. GitHub also serves as a social network for developers and their code. Developers can find each other, discuss project features and issues, and contribute to open source projects for free. GitHub is also a great way to showcase your work. Employers can view a prospective team member's code and previous projects to see if they would be a good fit for the team.

```

visit repos

https://github.com/freeCodeCamp/freeCodeCamp

https://github.com/getify/You-Dont-Know-JS

https://github.com/twbs/bootstrap

https://github.com/nodejs/node

all open source

## Questions?

## Instructor - 10 min
1. create repo on Github
2. public! with README (readme quick run through but very important)
3. adding a file
4. have students follow along on their computers (try)
5. copy https or ssh (discuss difference)
6. clone it on your computer somewhere
7. TIPs: 
Git Bash uses SHIFT+INSERT as the shortcut to paste.
Terminal uses COMMAND+OPTION+SHIFT+V as the shortcut to paste
8. cd into the new repo
9. create html file - add -A
10. commit -m 'atomic informative'
11. push
12. show how github now has new file

### It's ok to be overwhelmed
practice makes perfect

share this with students (uploading your code to github)

https://github.com/coding-boot-camp/front-end-16-week/blob/main/01-Lesson-Plans/01-html-git-github-module/02-intro-git-css-lesson/activities/01-Stu-Git/Steps%20To%20Upload%20to%20Github.pdf

## Students - 20 min 
slack out
```
Instructions:

Using GitHub and the command line, do the following:

Create a new public GitHub repository and name it whatever you like. Be sure to check the box for “Initialize this repository with a README.”

Next, clone the repo to your local directory.

Then create an HTML file inside the local directory.

Add, commit, and push the code to GitHub.

BONUS:

Create a new public GitHub repository, and name it zen-garden. Be sure to check the box for “initialize this repository with a README.”

Clone the repo to your local directory.

Go to CSS Zen Garden. Navigate to a few of the examples and choose a page that you like.

Download the HTML and CSS. Each page has a link to download the code, normally near the top of the page.

Move the HTML and CSS into your newly cloned repo and open the HTML in Chrome.

Use inspect element to identify a page element you would like to change in some way.

Change the CSS in any way you'd like.

Add, commit, and push the code to GitHub.
```

## Instructor Git Workflow - 10 minutes
Basic commands
git clone, add, commit, push, pull

tip - share = https://www.udemy.com/course/git-started-with-github/

## HTML Review (50 minutes)
### Instructor - 10 minutes
* front end development
* name 3 languages we are learning to create websites
* quiz on basics html
* html head, title, body, h1, anchor, p, a,  absolute vs local

## Instructor divs - 10 min
Divs: div tags are used to group elements into visually related segments. When you create a div, you create a section in your content. You can then use CSS to define how you'd like that section to be styled

```
<div class="Div">
 <h2>This is a heading for our div element</h2>
 <p>This is some text within our div element.</p>
</div>
```

section vs div (intro in html5)
block level 

http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf

default to div

## Students 20 min
student bio
it is 02-student-html - slack out instructions

## Instructor review - 10 minutes
```
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Activity 1: Basic HTML Bio</title>
</head>

<body>

  <!-- Site Header -->
  <header>
    <!-- h1: The most important headline -->
    <h1>Student Bio</h1>
  </header>

  <div>

    <!-- Section 1: Bio -->
    <section>
      <!-- h2: Tier-2 Headline (Not as important as the h1 header, but more than one allowed). -->
      <h2>Your Name</h2>

      <!-- Image with link -->
      <img src="http://placehold.it/200x200" alt="Your Name">

      <!-- Paragraph with embedded link -->
      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <!-- Section 2: Contact Info -->
    <section>

      <!-- h2: Tier-2 Headline -->
      <h2>Contact Info</h2>

      <!-- Unordered list -->
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>

    </section>
  </div>

</body>

</html>
```

## Break - 15 minutes
* instructor and ta's sync up meeting

## Instructor Demo - 15 minutes
```
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Basic CSS Example</title>

  <!-- Introducing the Style Tag! -->
  <!-- ========================== -->

  <!-- Now you can customize the look of your sites. Each rule in the style tag changes the appearance of its associated element (notice how each rule names an element from the HTML body). -->
  <style>
    /*
			NOTE: Commenting is a bit different in CSS. 
		  They start with forward-slash + asterisk 
		  and end with back-slash + asterisk.
		  */
    /* h1 heading tag */
    
    h1 {
      /* Put a 15-pixel margin at the bottom of the heading. */
      margin-bottom: 15px;
      /* Change the size of your font to 60 pixels high. */
      font-size: 60px;
      /* This will color the heading font white. */
      color: white;
      /* Align the text to the center of its enclosing element (e.g. div). */
      text-align: center;
      /* Underline the text. */
      text-decoration: underline;
      /* The background of the heading element will now be black. */
      background-color: black;
    }
    /* h2 heading tags */
    
    h2 {
      /* Put a 15-pixel margin at the top of all h2 headings. */
      margin-top: 15px;
      margin-bottom: 15px;
      font-size: 40px;
      text-align: center;
    }
    /* h3 heading tags */
    
    h3 {
      margin-top: 15px;
      font-size: 20px;
      text-align: center;
    }
    /* All img tags */
    
    img {
      /* 
				Center a block element in the middle of its enclosing tag.
				When you use the "auto" rule on both left and right margins, 
				your browser will do the math necessary to center a block element.
				*/
      margin-left: auto;
      margin-right: auto;
      /* Block display (more on this later) */
      display: block;
    }
    /* All p tags */
    
    p {
      text-align: center;
      font-size: 20px;
      /* Bold the text. */
      font-weight: bold;
    }
    /* All unordered list tags */
    
    ul {
      text-align: center;
      font-size: 35px;
      /* Give an element a solid border. */
      border-style: solid;
      /* Render the border 5 pixels thick. */
      border-width: 5px;
      /* Include bullets in the content flow. */
      /* More info here: http://www.w3schools.com/cssref/pr_list-style-position.asp */
      list-style-position: inside;
    }
  </style>
</head>

<body>

  <h1>Awesome Header</h1>
  <h2>Smaller Awesome Header</h2>
  <h3>Even Smaller Header</h3>

  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem consequatur unde aut dolores odio hic, accusamus recusandae ipsam illum enim voluptatibus obcaecati totam tempora eum quod sapiente. Corporis, quidem, culpa?</p>
  <img src="https://pbs.twimg.com/media/BsgYfMQCQAAWVKH.jpg" alt="Awesome" width="25%">

  <h3>Menu Links</h3>
  <ul>
    <li><a href="https://www.google.com">Google</a></li>
    <li><a href="https://www.facebook.com">Facebook</a></li>
    <li><a href="https://www.twitter.com">Twitter</a></li>
  </ul>

</body>

</html>

```
