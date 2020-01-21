- [Git](#git)
      - [ssh keys](#ssh-keys)
- [Node, npm](#node--npm)
      - [nvm](#nvm)
- [IDE](#ide)
      - [Intellij idea](#intellij-idea)
- [Operating system](#operating-system)
      - [Kubuntu](#kubuntu)
      - [Windows](#windows)
- [Pull requests / merge requests](#pull-requests---merge-requests)
  * [PR per feature](#pr-per-feature)
      - [PR #1](#pr--1)
      - [PR #2](#pr--2)
      - [PR #3](#pr--3)
  * [prerequisits of PR](#prerequisits-of-pr)
      - [CI](#ci)
      - [linting](#linting)
      - [Tests](#tests)
      - [Self testing](#self-testing)
      - [Release notes](#release-notes)
      - [Peer review](#peer-review)
      - [lead review](#lead-review)
      - [Close Old PR first](#close-old-pr-first)
      - [One PR per day](#one-pr-per-day)
- [Naming conventions](#naming-conventions)
      - [Git commit message](#git-commit-message)
      - [PR title](#pr-title)
      - [Function names](#function-names)
      - [Variable names](#variable-names)
      - [Notes for names](#notes-for-names)
- [Docs](#docs)
  * [API docs](#api-docs)
  * [Code docs](#code-docs)
- [Project management](#project-management)
  * [Agile](#agile)
      - [story points](#story-points)
      - [stand up](#stand-up)
      - [sprints](#sprints)
  * [Project management tool](#project-management-tool)
- [Coding and development](#coding-and-development)
  * ["Getting things done"](#-getting-things-done-)
      - [Do only whats required](#do-only-whats-required)
      - [Improvment](#improvment)
      - [Smart done](#smart-done)
      - [Definition of done](#definition-of-done)
  * [Coding practices](#coding-practices)
      - [libraries choice](#libraries-choice)
      - [ES6+ over old](#es6--over-old)
      - [TS over JS](#ts-over-js)
      - [Tests](#tests-1)
- [Efficiency](#efficiency)
      - [consistency](#consistency)
      - [reusable and modular code](#reusable-and-modular-code)
      - [CPP](#cpp)
- [Directory structure](#directory-structure)
    + [Frontend react based](#frontend-react-based)
    + [Backend nodejs](#backend-nodejs)
- [Configuring development environment](#configuring-development-environment)
      - [CORS restrictions](#cors-restrictions)
      - [Localhost nginx config (not needed unless asked)](#localhost-nginx-config--not-needed-unless-asked-)
- [Online remote groups](#online-remote-groups)
      - [Noise due to group talk](#noise-due-to-group-talk)
      - [Stay connected all the time](#stay-connected-all-the-time)
      - [Personal info](#personal-info)



# Git
#### ssh keys
add ssh keys so you do not have to type password everytime and also you will need it for getting some of our private modules via npm. https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent



# Node, npm
#### nvm
Do not install node by any other means but only use nvm. Follow this link and use latest LTS version of node. https://github.com/nvm-sh/nvm and https://github.com/nvm-sh/nvm#usage  (go for the latest LTS node version)



# IDE
#### Intellij idea
We encourage intellij idea **Ultimate edition** (very preferred). If you do not have the license, then **at least community edition**. If you do not have the **hardware resources**, you should get them to run intellij. If not, the last case (not preferred) is **vscode**.

Note that you should have **minimum of 4Gb ram**. Minimum **8Gb recommened** with most **unused plugins disabled** (else you it will consume a lot of cpu and memory)



# Operating system
#### Kubuntu
**Kubuntu** (with k) LTS (**ONLY LTS**) versions are preferred. https://kubuntu.com
#### Windows
If you use windows, you have to do the following in package.json (we have not made special windows commands yet as we mostly use and encourage Linux. This is the same setup we use on servers. So environment differences would be minimum).

exclude   `.`  (dot) and `/` slash at line starts

replace `/`  slashes with `\` blackslashes

replace   `;`  with `&`



# Pull requests / merge requests
## PR per feature
1. A feature should be divided into following **main parts/categories** and all PRs should be passed step by step. 
1. There can be more PRs than the below stated but these are the minimum and more sort of **broad categories**. 
1. Developer should write the `category number` in PR title. E.g `login page PR category #1`. Developer should **not work/extend code based on same/previous PR functionality, until the first PR is merged/approved**. This is because if there are issues in the intial PR, then the extended code based on that intial PR code will also have issues and consume more and more time. Same philosophy applies to PR categories. E.g do not go to category 2 unless 1 is approved.
1. You should work on some other feature/project during wait time.
#### PR 1
1. First PR should have all the possible **flow/achitecture with directories, files and empty functions** with //TODO comments inside (and interfaces if Typescript is used). This will tell the approace of the the developer, will help the developer envision the big picture/process/strategy. It will also get the code flow review at a much earlier stage and will eliminate gaps in expectations far ahead of time.
1. There are many approaches in industry to make flow before coding e.g UML diagrams, test cases (where test cases are written before writing actual code (TDD test driven development)), or simply writing empty functions/interfaces etc.
#### PR 2
Each function/part in PR #1 will be **implemented** (with unit tests if it is enforced in the project)
#### PR 3
This would be **final PR** and will also make sure that other parts of **application work in harmony** with the current task. If integration tests and/or automation tests are enforced in the project, this PR should have those too).

## prerequisits of PR
In order to get your code merged in master branch, you need to do the following. **Do not make a PR Pull request without the following first done**.
#### Create branch
Create a new branch by first cloning your project git repository, then creating a new branch from master. Start coding in it.
#### Pull from branch and master
Before pushing code for PR, make sure you have done CPP (commit(in your branch), pull (from your branch if others are working on it too. If not, then simply from master), push (to your branch))
#### CI
We do **contineuous integration (CI)** on github. **Make sure all checks are passed** and its a green tick with your pull request and commits.
#### linting
One of the CI steps is linting. You can **autofix** with npm scripts in package.json and then manually test for any lint errors before making a Pull request. **Manually fix** if something is not autofixed. As a side note, observe autofixed syntax and learn from it.
#### Tests
If your project has unit test/ integration tests/ automation tests enforced, do not file PR without them.
#### Self testing
All functionality should be tested before making a PR (self testing). Run and **test the functionality yourself first**.
#### Release notes
All PRs should have release notes about the functionality you made in that PR. It should briefly describe about the business flow, technical flow, any third party lib used and reason for its preference. This will have some **information that is not available in story points**. e.g any library used and why preferred, flow of code, technical precautions etc. This is very brief usually from **25 words to 100 words max**. 
#### Peer review
Next step is to have a peer review. (Peer should switch to branch, pull, check manually, then review code on github)
#### lead review
Next step is the have a final review by lead / manager
#### Issues in PR
If there are any issues in PR, they should be replied/typed in reply text box as fixed or replied to the question or a comment. Ultimately **all issues should be marked as resolved by the issue creater by clicking the resolve button**. The developer / PR creater should not press this button but only the issue creater should.
#### Close Old PR first
Always try best to close, finalize and **get old pull/merge requests first** before proceeding to new ones.
## Daily PRs routine
#### One PR per day
**There should be one PR per day. This is mandatory**. If you fail to get it approved, you have not achieved the full success of the day. You should file a PR before few hours of the day so it defintily get approved (assuming that it might have some issues and it might take you some time before dayend to resolve those issues and get the PR finally approved).



# Naming conventions
This can be best informed by the following examples. If you are not following these, your PR may get rejected on just the naming conventions. Clear and self explanatory names are critical and save people from a lot of frustration.
#### Git commit message
1. add backend min char check on password - login page
#### Branch name
1. frontend-form-validation--login-page
#### PR title
1. slicing done - login page
1. frontend form validation - login page
#### Function names
1. isValidEmail(email)// returns true/false
#### Variable names
1. userArray
1. userMap
1. users | userList //list of objects
#### Directory names
1. loginServices
#### Notes for names
1. Function and variable names can be a big long e.g even to 20 characters but they should **smartly** and **clearly** explain the meaning and purpose. I.e be **self explanatory**.



# Docs
## API docs
To be continued
## Code docs
To be continued



# Project management
## Agile
#### story points
#### stand up
#### sprints
## Project management tool
We had used Jira but prefer easy redmine.



# Coding and development

## "Getting things done"

#### Do only whats required
1. **Only do whats needed**. Nothing less, nothing more. Your time is precious. You should be focussed on your **specific targets and goals**. Your time on job is company's **valuable asset** as your targeted efficiency in it is the efficiency of the company! We want to see you valued.
1. If you see something wrong or a room for improvement, **ask permission beforehand** for any deviations because if you think something is beneficial, that may not be the case with a different perspective, it may have **side effects** or simply it may be be very **good but not needed at the time** or at the cost of the current time. So simply **ask lead/manager and discuss first**.
#### Improvment
1. You might be thinking **then, how do we improve the code/funcitonality?** Of course, you do but **in steps**. **First target is to complete in a 'good way' and not in a 'perfect way'**. 
1. Perfection is a step by step process and the steps may reach infinity in some cases. We will not be able to afford time loss for completion at the cost of long perfection sessions. 
1. So in short, get first stage workable. Get it approved, move to next stage, get it approved and so on. Do not try to reach stage 10 by wanting to learn and experiment for 9 prior stages in one go. 
1. **If your code**, on the other hand, **is below standards**, you will ultimately get **PR issues anyway**... Remember them and do not repeat them. So you/your code improves any way by default. 
1. But keep a fine line between personal part of pure self learning (with self motive only) and self experimenting vs completing the task as priority and **learning through that** (which will be done any way during the process so everyone gets happy).
#### Smart done
Suppose you have 10 things in your todo list. **5 things 100% done is better than 10 things done 50% each**.
#### Definition of done
Completion of a task with minimum acceptable qaulity (does whats needed, passes lint and code review etc).
## Coding practices
#### libraries choice
You should have very good reasons to choose a library. In most of the cases, you should **ask lead before choosing a library**.
#### ES6+ over old
**Always use ES6+ syntax over old. Take it as a mandatory rule**.
#### TS over JS
If your project is Typescript based, **use Typescript wherever possible**.
#### Tests
We use **Jest** as the testing library for unit tests and integration test. For automation test, the choice is of project manager.

## Frontend
#### **Only** use css/scss (scss preferred) for libraries like material ui etc that offer both Javascript based style configurations and css based style configurations. Put css/scss code in separate files for each component.

# Efficiency
#### consistency
Be consistent in choosing, using, following architecture, libraries, patterns
#### reusable and modular code
Do not repeat your self
#### CPP 
commit, pull, push in **same sequence**. Do this as frequently as you can. Sequence is important. Commit first, then pull (from your branch AND from master at least), then push (to your branch). E.g For a **team of X number of people, you should do it X times a day**. Ie in a team of 3 people, you should do this at least 3 times a day. 



# Directory structure
### Frontend react based
To be continued
### Backend nodejs
To be continued



# Configuring development environment
#### CORS restrictions
If you get CORS errors, you can install browser plugin (one called `allow cors` for chrome). You have to hit the big icon and make it colored to activate it.
#### Localhost nginx config (not needed unless asked)
To be continued



# Online remote groups
#### Noise due to group talk
If you feel theres **too much voice conversations** in remote group, you can **mute the volume** but you should **be alert for any chat messages**. If some one wants to talk to you, (s)he should ping you on chat. You should do the same.
#### Stay connected all the time
You should stay connected to group collaboration software all the time
#### Personal info
1. Sharing of any personal information or discussing anything not related to work/current tasks is treated as a miss conduct.
1. Using any personal email, phone or contact in any platform, such as but limited to, github, collaboration, chat etc tools is treated as a miss conduct.
