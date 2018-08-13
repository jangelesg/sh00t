<img src="https://user-images.githubusercontent.com/11267537/43043618-29ab7286-8db5-11e8-9603-71b30596d047.png" width="250" />

```
A Testing Environment for Manual Security Testers
```

Sh00t
- is a task manager to let you focus on performing security testing
- provides **To Do** checklists of test cases
- helps to create bug reports with customizable bug templates


### Features:
- Dynamic Task Manager to replace simple editors or task management tools that are NOT meant for Security
- Automated, customizable Security test-cases Checklist to replace Evernote, OneNote or other tools which are NOT meant for Security
- Manage custom bug templates for different purposes and automatically generate bug report
- Support multiple Assessments & Projects to logically separate your different needs
- Use like a paper - Everything's saved automatically
- Export auto generated bug report into Markdown & submit blindly on HackerOne! (WIP)
- Integration with JIRA, ServiceNow - Coming soon
- Export bug report into Markdown - Coming soon
- Customize everything under-the-hood


### Installation:
Sh00t requires Python 3 and a few more packages. The simplest way to set up Sh00t is using Conda Environments. However, Anaconda is optional if you have Python 3 and pip installed - you can jump to **step 4** below.

**Pre-requisite - One time setup:**

1. Install the minimal version of Anaconda: [Miniconda](https://conda.io/miniconda.html) and follow 
the [installation instruction](https://conda.io/docs/user-guide/install/index.html). Remember to 
reload your bash profile or restart your terminal application to avail conda command. For windows, launch `Anaconda Prompt` and run all the below commands in that window only.
2. Create a new Python 3 environment: `conda create -n sh00t python=3.6`
3. Activate *sh00t* environment: `conda activate sh00t`. If you see an error message like 
`CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.`, you have to manually enable conda command. Follow the instructions shown with the error message. You may have to reload your bash profile 
or restart your terminal. Try activating sh00t again: `conda activate sh00t`. You should be seeing `(sh00t) XXXX$` in 
your terminal.
4. Clone or download the latest project into a location of your choice: `https://github.com/pavanw3b/sh00t`. `git clone` requires installation of Git.
5. Navigate to the folder where sh00t is cloned or downloaded & extracted: `cd sh00t`. Note that this is the outer-most 
*sh00t* directory in project files. Not *sh00t/sh00t*.
6. Install Sh00t dependency packages: `pip install -r requirements.txt`
7. Setup database: `python[version NUMBER] manage.py migrate | i.e python3 manage.py migrate `
8. Create an User Account: `python manage.py createsuperuser` and follow the UI to create an 
account.
9. Optional but recommended: Load  Test Cases from OWASP Testing Guide (OTG) and Web Application Hackers Handbook (WAHH): `python reset.py`.

That's all for the first time. Follow the next steps whenever you want to start Sh00t.

**Starting Sh00t:**

If you have Python 3 installed on your machine, you can jump to **Step 3**.

1. For Linux/Mac, Open Terminal. For Windows, open `Anaconda Prompt`.
2. Activate sh00t environment if not on yet: `conda activate sh00t`
3. Navigate to sh00t directory if not in already: `cd sh00t`
4. Start Sh00t server: `python manage.py runserver`
5. Access [http://127.0.0.1:8000/](http://127.0.0.1:8000/) on your favorite browser. Login with the user credentials 
created in the one-time setup above.
6. Welcome to Sh00t!
7. Once you are done, stop the server: `Ctrl + C`
8. [Optional] Deactivate sh00t environment to continue with your other work: `conda deactivate`.


### Upgrade:
* Navigate to the folder where sh00t was cloned
* Stop the server if it's running: `Ctrl + C`
* Pull the latest code base via git: `git pull` or download the source from github and replace the files.
* Navigate to sh00t directory: `cd sh00t`
* Activate sh00t environment if not on yet: `conda activate sh00t`
* Make the latest database changes: `python manage.py migrate`
* Start the server: `python manage.py runserver`

### Troubleshoot:
Sh00t is written in Python and powered by Django Web Framework. If you are stuck with any errors, Googling on the error 
message, should help you most of the times. If you are not sure, please [file a new issue on github](https://github.com/pavanw3b/sh00t/issues/new).

### Glossary:
- **Flag:** A Flag is a target that is sh00ted at. It's a test case that needs to be tested. Flags are generated automatically based on the testing methodology chosen. The bug might or might not be found - but the goal is to aim and sh00t at it. Flag contains detailed steps for testing. If the bug is confirmed, then it's called a sh0t.
- **Sh0t:** Sh0ts are bugs. Typically Sh0t contain technical description of the bug, Affected Files/URLs, Steps To Reproduce and Fix Recommendation. Most of the contents of Sh0t is one-click generated and only the dynamic content like Affected Parameters, Steps has to be changed. Sh0ts can belong to Assessment.
- **Assessment:** Assessment is a testing assessment. It can be an assessment of an application, a program - up to the user the way wanted to manage. It's a part of project.
- **Project:** Project contains assessments. Project can be a logical separation of what you do. It can be different job, bug bounty, up to you to decide.

### How does it work?
Begin with creating a new Assessment. Choose what methodology you want to test with. Today there are 330 test cases, grouped into 86 Flags, belonging to 13 Modules which are created with reference to "Web Application Hacker's Handbook" Testing Methodology. Modules & Flags can be handpicked & customized. Once Assessments are created with the Flags, now the tester has to test them either manually, or semi automated with the help of scanners, tools or however it's required, mark it "Done" on completion. While performing assessment we often come with custom test cases that is specific to certain scenario in the application. A new Flag can be created easily at any point of time.

Whenever a Flag is confirmed to be a valid bug, a Sh0t can be created. One can choose a bug template that matches best, and sh00t will auto fill the bug report based on the template chosen.


### Screenshots:

#### Dashboard:

![dashboard](https://user-images.githubusercontent.com/11267537/43355841-9f6167e4-9281-11e8-87fe-761fa35ddc3c.png)

#### Working on a Flag:

![flag](https://user-images.githubusercontent.com/11267537/43355838-9ee99e58-9281-11e8-8724-b9e726fdc58d.png)


#### Choosing Methodology and Test Cases while creating a new Assessment:
![new-assessment](https://user-images.githubusercontent.com/11267537/43355840-9f3a3368-9281-11e8-8afd-0467a4ac00b4.png)

#### Filing a bug pre-filled with a template:

![new-sh0t-from-template](https://user-images.githubusercontent.com/11267537/43355839-9f117630-9281-11e8-8a33-a9b5babae698.png)


### Who can use Sh00t?
- Application Security Engineers: Pentesting & Vulnerability Assessments
- Bug bounty hunters
- Independent Security Researchers
- Blue team, developers who fix
- Anybody who wants to hack

### Implementation details:
- Language: Python 3
- Framework: Django Web Framework
- Dependencies: Django REST Framework, TinyMCE (Managed by /requirements.txt)
- UI: Bootstrap - Responsive



**Contribution:**
- Pavan: [@pavanw3b](https://twitter.com/pavanw3b)
- [Aditya Ganapathy](https://github.com/adityadev91)

**Credits:**
- Hari Valugonda
- Mohd Aqeel Ahmed
- Ajeeth Rakkappan
