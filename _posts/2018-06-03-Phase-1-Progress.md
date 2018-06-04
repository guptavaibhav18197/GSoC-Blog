---
layout: post
title: "Phase 1 Progress"
---

By the end of community bonding period we were done with all the **requirements elicitation** and **designing** process. In the community bonding period I also did the installation of the required tools : `apache-server`, `flask` and it's dependencies, `MySQL` and other 3rd party libraries required.

This phase is directly headed towards the coding part of the project.

# [](#header-1)Decisions made post community bonding period
We decided to go with **MySQL** under the abstraction of _flask-SQLAlchemy ORM_.

## [](#header-2)Rationale for using MySQL

*   Not only it's very popular and easy to use, but also
*   there's a great support for it.
*   Security wise also it's very reliable.
*   Also, switching from MySQL to Maria-DB is quite simple but the reverse is not true. So we can switch to Maria-DB in future if the need be.

# [](#header-1)Progress made so far
I am strictly following the timeline proposed in the project proposal and have been able to convey all the deliverables as per the timeline as of now. The Phase 1 coding tasks have been completed. Apropos code has been pushed to the github repository [Rapid Annotator](https://github.com/guptavaibhav18197/rapidannotator).

## [](#header-2)Directory Structure / File Hierarchy
With blueprints, we can have possibly 2 different Directory Hierarchy choices **functional** versus **divisional**. By examining the pros and cons of both I decided to go with a _hybrid_ of the 2.

We will divide the main Rapid Annotator into several smaller packages which will be related to specific tasks like **admin package** will manage all the control the admin has over all application just as in _divisional approch_. Borrowing from _functional approach_ we will have code that can be shared across all the packages like generic jinja-macros, jinja-filters, WTForms-validatorcss, css and other reusable code.   

So the final Directory Structure is a below
![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/dirStructure.png)

## [](#header-2)Code Implemented
As explained above the entire code base is divided into many smaller packages using _flask_ **blueprints**. Below is the list of packages of Rapid Annotator.

Packages of Rapid Annotator

| Functionality             | Name assigned         |
|:--------------------------|:----------------------|
| Login/Registration        | frontpage             |
| Home Page                 | home                  |
| Add New Experiment        | add_experiment        |
| View Experiment           | view_experiment       |
| Annotate “This Experiment”| annotate_experiment   |
| Admin Page                | admin                 |

This phase deals with working on first 3 packages namely : `frontpage`, `home` , `add_experiment`. Broadly this phase aims at finishing the `frontpage` and `home` packages completely and start working on `add_experiment` package.

### Backend Implementation

*   Created **User** relation.
*   Created **Experiment** relation.
*   Created **ExperimentOwner** association table to make _many to many_ relation between User and Experiments.
*   Created **AnnotatorAssociation** association object to make _many to many_ relation between User and Experiments.

An _association object_ was needed since this relation had additional fields of `start`, `end` and `current` integer fields indicating the range of the files that specific User has to annotate and the current file number that specific User is annotating.

### frontpage package

*   Created UI for Login Page.
*   Got `Flask-SQLAlchemy` working and connected it to MySQL server.
*   Wrote **validators** for making sure username attribute follows a specific `regex` pattern.
*   Created **Login Form** and **Registration Form** and fields using FlaskForm of `flask_WTF` and fields of `WTForms`.
*   Linked it to database and finished user registration.

### Generic Code

*   Created generic macros for rendering similar structured information like forms.
*   Created a generic **base template** that will be common to all the tabs and pages via `Jinja template inheritance`.
*   Enhance UI of the basic structure of base template

### home package

*   Displayed 2 tabs: **My Experiments** & **Experiments to Annotate**.
*   UI details and made a responsive front-end.
*   Created **filters** required to render specific stuff like datetime in specific format.

### add_experiment package

*   Added Owner dropdown displaying list to choose owner from.
*   Added Annotator dropdown displaying a list to choose annotator from.
*   Used Javascript's `jQuery` library to make _ajax_ requests to add Owner and Annotators.

## Deviation from the proposal

### Changes in the model

*   In the `User model`: I have clubbed `first name` and `second name` : into `fullname`.
*   In the `User model`: `Password Salt` is not included in the model: because we are using `flask_bcrypt` that recommends using the inbuilt salt value. So, I am now storing Password Hash under the name password itself.
*   In the `Experiment model`: `created_at` and `status`[complete/incomplete] attributes have been added for ease of access by the Owners and Annotators.  
