## Summary of dev tasks and time

- 05-08-2019 x Upload to github
- 05 x Readme.md
- package.json description

- 06-08-2019 !!! Form mobile view fill issue with background color check in the phone

- 05-08-2019 x Change text placeholder Message form

- x variable widths for mobile, vs desktop:
  - x use bulma classes
    - x Put lion background in main.scss and use an if mobile statement to remove the lion
    - x Add input placeholder for other browsers

* x Child component, slider of detailed employee info

  - x Get state of position in array of employees.json
  - x active property to point to index in object array
  - x slide on phone, with finger

* 6-08-2019 Router for pages per employee

  - Start with slider component

* 6-08-2019 x Navbar component
  - x Alion

--------- First Iteration Saturday/Sunday --------------------

- Load json in vue main app component
  03-08-2019:

  - x Pass only an object to child component, an object per new employee card created
  - x Pass json file to child component
  - x Make json file

- Styles: Get/Recreate Alion styles
  04-08-2019

  - x Font
  - x Spacing between cards
  - x favicon Alion for website
  - x !!! import icons to use with bulma !!!

- Child component employeecards
  03-08-2019:

  - x Render 3 cards per row
  - x How to render 3 cards per row when we have 9, multi-line columns
  - x read more button (animated)
  - x Create row and column per card if number of cards is higher than n ammount of columns then create a new row and new columns per card
  - x Add hover to styles
    - x On hover scale card
    - x Change color of name animation, as a keyframe

- Form validation for contact
  04-08-2019:
  - x Conditional classes for input field
  - x Set v-model
  - x methods for validation, check if name, age, and message is valid...
  - x The name of the field is required
