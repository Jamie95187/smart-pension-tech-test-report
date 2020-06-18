# Smart Pension Tech Test

## Setting up

After cloning repository with `git clone git@github.com:smartpension/smart-cs-support-test.git` I realised that I am unable to open the files with Atom.

Following the instructions to run the application, using the command `bin/setup`. I was prompted to update my yarn version. The gem dependencies and databases were set up via the bundle installation.

![Image of database installation](./images/database-setup.png)

I started the Rails server by typing `rails s` into the terminal.

![Image of starting rails](./images/starting-rails.png)

## Navigating the website

`localhost:3000` - works fine and has two buttons *'Create New Company'* and *'Companies List'*

`localhost:3000/companies/new` - can navigate to the link by clicking *'Create New Company'* button on home page. We are presented with a form with a text input for *'Name'* of company and a text area to fill in called *'Details'*. A user can fill in duplicated company names and details. They can also fill in a blank input for both entries (possible error one). At the bottom of the form there are two buttons. *'Save'* and the other *'Back to companies list'*.

`localhost:3000/companies/id` - the id param in the URL represents the newly added company's id. The new listing is appended to the end of the Company table in the database. However the data rendered on the table on this page always shows the first entry of the database (error two). There are two buttons at the bottom of the page *'Add Employee'* and *'Back to companies List'*.

`local:3000/companies/1/employees` - clicking on the *Add Employee* renders a form to fill in with two text inputs. An input for Forename and another for Surname. There are two buttons at the end of the form named *'Save'* and *'Back to employees list'*. If the user leaves one of the inputs blank they are prompted with an error message. If the user leaves the 'Forename' input blank they are given an error with 'Forename can't be blank' and 'Middlename can't be blank' (possible error three). Filling in both inputs still gives an error of 'Surname can't be blank' (error four). The employees' id are incorrectly labelled on the table (error five).

`local:3000/companies` - this page renders a table listing all the companies that are saved in the database. There are two buttons for each listing called *'Show'* and *'Destroy'*. Destroy prompts the user with an alert and asks if they are sure they would like delete this listing. The show button will navigate the user to the page `localhost:3000/companies/id`. At the bottom of the table there is a button that navigates to creating a new company.

## Possible solutions

## Error One

After creating your company you are redirected to Mickey's Plaice employees. Would be better to be redirected to your company's employees.

## Error Two

Manually typing the URL localhost:3000/companies/id followed by an index that is out of bounds of the database returns an error page. Would be better to give the user a warning message instead of code error.

## Error Three

Trying to edit an employees detail gives an error couldn't find employee id=''. Button statically renders the next page instead of dynamically?
