# Contents

- [Graded Feedback](#Graded Feedback)
  - [Week 01](#Graded Feedback#Week 01)
  - [Week 02](#Graded Feedback#Week 02)
  - [Week 03](#Graded Feedback#Week 03)
  - [Week 04](#Graded Feedback#Week 04)
  - [Week 05](#Graded Feedback#Week 05)

# Graded Feedback
## Week 01
Hello XXX,

Below is my feedback for your Workshop #1 Assignment:


Task 1

all files are spelled in lowercase

no spaces in file/folder names

used dashes instead of spaces for file/folder names

correctly add lobster google font

correctly add bootstrap 4 CDN css

correctly add bootstrap 4 CDN js (with jquery and popper)


Task 2

Added formatting to the web page using the Bootstrap grid's container, row, and column classes.


Task 3

Proper bootstrap classes were added to hide paragraphs on small displays

Links updates per instructions

correct files uploaded

used full-page screenshots

bonus (not required by great to have)

aboutus.html validate HTML

style.css validates CSS

added Github URL for workshop #1 repo

note: you are missing your package.json file so you can't use your scripts to run lite server

Overall, great job on your first workshop. Keep up the great work

## Week 02
Hello STUDENT_NAME,

Task 1

Added react-lake-thumb.jpg

Add responsive bootstrap styles to images

Task 2

Added a new row

Inside new row added a column 6 for breakpoints small and up

Added the requested spacing

Added a card div with a heading and a body

The card body has a form with label, select and options

The label takes half the screen on small viewports

The select takes up the remaining space

Added a date field

Added a Search button

Task 3

Added code to link the Reserve Campsite to redirect to form on the bottom of index.html

The Reserve Campsite button is styled with Bootstrap and should be responsive

Bonus:

index.html DOES NOT (HTML validator) (please review this and fix)

Added Git and shared GitHub repo URL - awesome!
Overall, great work!

## Week 03

Hello ENTER_STUDENT_NAME,

I have provided feedback to your workshop #3 assignment below:

Task 1

Removed the code related to the tooltip from the "Reserve Campsite" button in the jumbotron

There are four different attributes added to the button to support the tooltip Remove all of them

Removed the JavaScript at the bottom of the page that you added to support tooltips

Also remove the href attribute of the button

Added the correct data-* attributes to activate the modal

Used the id of #reserveModal to trigger the modal

Task 2

Created reservation form modal

Beneath the closing </header> tag in index.html, Created a new modal

Deleted all the code inside the form element in this new modal

In the first div of the new modal you just copied, changed the id to reserveModal

Added the modal-lg class to the div that has the class of modal-dialog

Replaced the modal title text Login with the text Reserve a Campsite

Added the classes bg-info and text-white to the div with the class modal-header to match the screenshot provided in the workshop instructions 

Moved content inside the form element in the modal 

Above submit button element, added another button with the text of Cancel

Gave cancel button the attribute of data-dismiss="modal" and used a Bootstrap class to give it the color to match the screenshot image in the workshop instructions 

Deleted any remaining code for the reservation form that was there

Task 3

Added a radio button group to the reservation form inside the modal to allow the user to select between Tent and RV campsites 

Added a new form-group row div, below the Date form-group row div

Added a label inside the row with the text "Campsite Type"

Applied the column class to it that will cause it to take up half the row for small and up viewports

Applied the col-form-label class to this label as well 

After this label element, added a div with a column class of col-2

Applied the btn-group and btn-group-toggle classes as well to this column div, and give it a data-toggle="buttons" attribute as well

For the rest of this button group, changed it to use the Bootstrap button color classes shown in the screenshot provided in workshop instructions

Used the name "siteType" for both inputs

Then for each, used an id of either "siteTent" or "siteRV" and a value of either "tent" or "RV"

Optional

Updated Git Repo with workshop 3 code

HTML validates!

Overall, great job. Keep up the hard work!

## Week 04
Hello ENTER_STUDENT_NAME,

Here is my feedback for your Week 04 Workshop:

Task 1

Removed the data-* attributes from the Reserve Campsite button in the Jumbotron that activates the reservation modal

Replaced them with an id called reserveButton.

Also removed the data-* attributes from the Login link in the navbar that activates the login modal

Replaced them with an id called loginButton.

Task 2

Added JavaScript (in the form of jQuery) to the scripts.js file that will activate the Reserve Campsite and Login modals when the corresponding button is clicked.



Task 3

In index.html, Removed the "bg-info" and "text-white" classes.  

In styles.scss file, created a new color variable at the top, named $color-teal with a value of #17A2B8.

At the bottom of the styles.scss fileused the nesting functionality of Sass to set up CSS rules for the Reserve and Login modals, using their ids to set up the first level of the nesting, then the class "modal-header" for the inner level. 

Wrote rule for the Reserve modal's modal-header so that it uses the background color of $color-teal. Also set it up to have white text.

Write the rule for the Login modal's modal-header so that it uses the background color of $color-mid. Also set it up to have white text.

npm start compiles SCSS to CSS and colors render correctly


Optional

HTML validates - Awesome!

Git Repo for Workshop Assignments exists and is updated with Week 04 adds and commits - Awesome!

Overall, you are doing a great job in the class and the workshops. I hope you are making progress on your project this week. Keep it up!

## Week 05

Hello ENTER_STUDENT_NAME,

Here is my Feedback on your Workshop #5:

As promised here is the JavaScript for the solution. Please review it and compare it to your solution. There is never one perfect solution in JavaScript. There are many ways to tackle this problem and this is just one way:

https://gist.github.com/kingluddite/5570e20893f47ac32c645728cecbbb4f

Task 1

You will use Bootstrap to adjust the user interface. 

Used Bootstrap class to vertically align the text "My guess is" in the row so that it is centered instead of top-aligned. 

Modified the column class for the first column in the first row of the grid so that it spans across 2 out of the 12 columns of the row for small and up viewports. The two columns in the row should stack vertically for XS viewports. 

Used a Bootstrap spacing utility class, give the first row a Bootstrap class that will increase the bottom margin of the row, as seen in the screenshot below.

Task 2

Added a way to reset the game.

"Reset" button only appears once the correct guess has been made, and when it's clicked, it causes the game to reset to the very beginning setup where it says 'Think of a number between 1-100 and click the blue button when you're ready.' in the UI

Task 3 

Evaluate whether you are giving it nonsensical answers so that it doesn't play forever

Bonus Challenge

Improved the game further than just starter code

Submitted URL of forked 

Overall, great effort in this workshop and all workshops xxx. It was a pleasure learning with you. Keep working on your Portfolio project and keep coding. You got this!
