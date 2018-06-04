---
layout: post
title: "Phase 1 Progress"
---

By the end of community bonding period we were done with all the **requirements elicitation** and **designing** process and this phase is directly headed towards the coding part of the project.

# [](#header-1)Decisions made post community bonding period
We decided to go with **MySQL** under the abstraction of _flask-SQLAlchemy ORM_.

## [](#header-2)Rationale for using MySQL

*   Not only it's very popular and easy to use, but also
*   there's a great support for it.
*   Security wise also it's very reliable.
*   Also, switching from MySQL to Maria-DB is quite simple but the reverse is not true. So we can switch to Maria-DB in future if the need be.

# [](#header-1)Progress made so far
I am strictly following the timeline proposed in the project proposal and have been able to convey all the deliverables as per the timeline as of now. The Phase 1 coding tasks have been meet. Apropos code has been pushed to the github repository [Rapid Annotator](https://github.com/guptavaibhav18197/rapidannotator).

## [](#header-2)Directory Structure / File Hierarchy
With blueprints, we can have possibly 2 different Directory Hierarchy choices **functional** versus **divisional**. By examining the pros and cons of both I decided to go with a _hybrid_ of the 2.

We will divide the main Rapid Annotator into several smaller packages which will be related to specific tasks like **admin package** will manage all the control the admin has over all application just as in _divisional approch_. Borrowing from _functional approach_ we will have code that can be shared across all the packages like generic jinja-macros, jinja-filters, WTForms-validatorcss, css and other reusable code.   

![image](/https://guptavaibhav18197.github.io/GSoC-Blog/thumbnail-jumbo.png)


## [](#header-2)Code Implemented
The entire code base is divided into many smaller packages using _flask_ **blueprints**.

Packages of Rapid Annotator

| Functionality             | Name assignmed        |
|:--------------------------|:----------------------|
| Login/Registration        | frontpage             |
| Home Page                 | home                  |
| Admin Page                | admin                 |
| Add New Experiment        | add_experiment        |
| View Experiment           | view_experiment       |
| Annotate “This Experiment”| annotate_experiment   |


*   Created UI for Login Page.
*   Setup Flask-SQLAlchemy and create User relation in it.
*   Created Login form and fields using FlaskForm of flask_WTF and fields of wtforms [reference].
*   Linkd it to database and finish user registration.

Create generic macros for rendering similar structured
information like experiments’ and files’ thumbnails.
b. Create a generic base template that will be common to all the
tabs and pages via Jinja template inheritance.
c. Enhance UI of the basic structure of base template

Implementing Home page: It involves
a. Displaying 2 tabs: My Experiments & Experiments to Annotate.
b. UI details and making a responsive front-end.
























asdf
