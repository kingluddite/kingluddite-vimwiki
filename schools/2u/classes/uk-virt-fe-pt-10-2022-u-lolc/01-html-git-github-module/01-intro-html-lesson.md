## 01-intro-html-lesson
Tomorrow afternoon, before your very first class, we will have a quick introductory session for you at 6:00pm sharp. In this session we'll review important information that will help answer some of your questions regarding graduation requirements, class management, live support and more.
The link to join this session will be https://zoom.us/j/95971553349, and the zoom room will open at 5:45pm

6pm - Make sure you are recording

1. Hello
2. Slides - https://docs.google.com/presentation/d/1bVwosLLIFv12kaXCv3J4qPVp5oZFIszQ2GHL0QAbBGA/edit#slide=id.gc0b4ecbb75_0_1187
3. Slides on Prework
* Instructor review to make sure work (share google doc link on slack resources) 5 minutes (show how to audit)

Have students fill out form and then breakout rooms for students with issues
  * Slack - open it, desktop local install not using the web client
  * VS Code
  * Terminal (mac)
  * Git Bash (windows)
  * GitHub
  * Git - $ git (should see a series of lines) not "git command not found"
  * Git SSH - ssh -T git@github.com (it will ask you for a passphrase - tied to your account) - provide it (letters will not appear as you type) and press enter - you should get a welcome message - if you don't get welcome message - you need to work through this URL - https://help.github.com/articles/generating-an-ssh-key/

15 minute break (help students who need to complete prework)

4. Console (35 minutes)
* cd
* cd ~
* cd ..
* ls
* pwd
* mkdir <FOLDERNAME> lower case - no spaces, use dashes
* touch <FILENAME> same naming convention as folder
* rm -r <FOLDERNAME>
* open . (open the current folder - mac)
* open <FILENAME> (open file - mac)
* explorer <FILENAME> (open file - windows)
* explorer . (opens the current folder - windows)
* tabbing (autocomplete)

## Student Activity - Slide Console Commands (10 minutes)

## 5 minutes - break out rooms

Have students use Slack to discuss with the process of creating files, removing files, etc.

Also have students explain to one another a high-level definition of "front end development."

Briefly have students explain the answers back to you.

## Web pages - 15 minutes
HTML
CSS
JavaScript
Coding
Chrome browser and Chrome Dev tool (CDT) POWERFUL TOOL!
www.google.com > Inspect (explain HTML and CSS)
wall html, paint on wall, css, electrical sockets in wall JavaScript
change an element on page (not hacking)
(not saved) refresh to see changes go away (independent of original HTML/CSS)
also change the CSS via CDTs

Any questions?

## Student - Examine Wikipedia Slide (5 minutes)
* take a screenshot and share on "live" slack channel

## Instructor Review (5 minutes)
have everyone refresh page - changes all gone
why are changes gone?
how could we change code on this site for real? (need access to the wikipedia servers - or use wikipedia's community editing process)
editing CSS and HTML is not permanent but a tool you will use all the time in this class and moving forward as a developer
This is why knowing and understanding HTML and CSS are important and why we are starting with these technologies this week

## Instructor - HTML - 15 minutes
1. Open VS Code (IDE)
* this kind of app enables progammers to:
edit source code, build executables, and perform debugging (all in one consolidated environment!)

2. Create new HTML file from scratch (no boilerplate)
ask student to follow along - if you fall behind don't stress you'll have time later to create your own HTML file

open and hand code this - and talk about the different parts

https://github.com/coding-boot-camp/front-end-16-week/blob/main/01-Lesson-Plans/01-html-git-github-module/01-intro-html-lesson/activities/03-Ins-HelloHTML/HelloHTML.html

open lesson plan  to walk through and comment points

```
<!-- All HTML documents must start with a declaration. -->
<!-- Unlike other elements, this line of text is not actually an HTML tag. -->
<!-- Instead, it lets the browser know what document type to expect so that it renders properly. -->
<!DOCTYPE html>
<!-- The html tag operates in much the same way as the !DOCTYPE declaration does. -->
<!-- It tells the browser that the contents of this file are written in HTML. -->
<!-- Unlike the !DOCTYPE declaration, however, the HTML tag has both a start point—<html>—as well as an end point—</html>—with all other HTML content contained within. -->
<!-- Most HTML elements function in this way, acting as containers for the content written between their start tag and their end tag. -->
<html lang="en-us">
  <!-- This element (<head>) operates as the container for metadata (data about data) and is always placed between the HTML and body tags. -->

  <head>
    <!-- This metadata contains information about that HTML document that is not displayed by the browser, including the document's title, styles, scripts, and search engine information. -->
    <meta charset="UTF-8" />
    <!-- <title> - Placed within the <head> element, the title element defines the title of the document and is required in all HTML documents. -->
      <!-- This element defines a title in the browser tab, provides a title for the page when it is added to favorites, and displays a title for the page in search engine results. -->
    <title>Hello World</title>
  </head>

  <!-- This <body> element contains the actual content that will be displayed when the webpage is rendered. -->
  <body>
    Hello World!
  </body>
</html>
```

## View in browser
* Show how code looks different to the rendered browser web page
* talk about comment tags 
* not dipslayed in browser (just for you and other developers)
* short sentence or multiple lines of text

## Any Questions?

### Create first web page activity - students 10 minutes
* instructions on slide
* Bonus: Feeling fancy? Add a line break and another sentence saying, "Hello, world!"

### Review html
* walk through how to to my first HMTL page (open and talk about the lines

https://github.com/coding-boot-camp/front-end-16-week/blob/main/01-Lesson-Plans/01-html-git-github-module/01-intro-html-lesson/activities/04-Stu-FirstHTML/solved/FirstHTML.html
* naming convention (lowercase!)

## Instructor - working from 01-HelloHTML
h1
p
ul li
ol li
a href to absolute site
br (empty element aka void element)
<br> or <br />
img src point to image (<img src='https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSEHt_y93yyr0K91auu97DDEA7vVD9rSuD3uZeTiRaH9SabYO8-64fcWS8ycXQ&usqp=CAc' alt =’flamingo’>)
jpeg vs png vs svg vs gif

### Any questions?

## Students - Build HTML (15 minutes)
slack instructions (lesson plan)
breakout rooms
share screen help each other complete this

```
Keep your HTML code from the previous exercise available for them to see while they work, but don't send them the code just yet.
Instructions:

In a new HTML file, create the basic structure of an HTML document and include the following in it:

DOCTYPE declaration
Head tag with a title tag
H1 tag with a title of your choice
Embedded image
Three links that you will create:
Make the first link target="_blank" so that it opens a new tab when clicked on.
Make the second link bold.
Make the third link a placeholder, so it goes nowhere.
Hint: You should be looking up at the screen pretty often. :P

Bonus:

Create an ordered list of steps to make a sandwich.
Create an unordered list of five bands/musicians you like.
Create a table with two columns (animal class and animal name) and four rows of animals.
Use an alternate way of separating links without line breaks.
Embed a YouTube video of your favorite band/musician.
```

## Instuctor review
https://github.com/coding-boot-camp/front-end-16-week/blob/main/01-Lesson-Plans/01-html-git-github-module/01-intro-html-lesson/activities/05-Stu-SecondHTML/solved/SecondHTML.html

Key elements like <!DOCTYPE html>, <html>, <head>, <h1>, and links.

Specifically, we haven't taught them how to use target="_blank", so be sure to explain how this modifies the link target.

Also make sure to explain how they can separate links using <p> tags! 

Tips
Good indentation practices: In fact, if you have time, un-indent everything by highlighting everything and hitting ctrl-j and then re-running the code. Show students that the code will still work but ask them to try to read it. Explain that unformatted code is awful to maintain—because no one can read it!

Next, try showing students how to easily format an HTML document. Simply select all of the content on the page using ctrl+A, right-click, and select format! Such an easy thing, but it makes a huge difference!

tables
Finally, you'll notice we haven't covered tables yet. Building HTML tables is a pain (just like in markdown). We've omitted this topic but recommend demonstrating it and asking students to build one as an extension topic if you have time.

html validator

## Recap
make sure all prework completed
terminal commands review
basic HTML page structure and elements

jan 12th project 1 presentation
feb 23rd project 2 presentation
1) askbcs first
2) https://tinyurl.com/BootcampTutorTeam  (sign up for tutor)
deadline for drop (tuesday 10/25/2022)






