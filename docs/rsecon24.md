# :snake: RSECon24 Workshop: Effortlessly creating Python packages with good practices

!!! info Session

    Time: 14:30-15:45 Tuesday, 3 September, 2024

    Location: 2.16 (Classroom)

    [Submission link](https://virtual.oxfordabstracts.com/#/event/49081/submission/99)

!!! note

    These notes are for the presenter and may change.

---
## :watch: 4 mins - Introduction - Presentation


---
## :watch: 1 min - Check the requirements

Instructions can be found at [https://github.com/fdiblen/RSECon24](https://github.com/fdiblen/RSECon24)


!!! note

    Use `bash` shell with a simple prompt by running:

    ```
    export PS1='$ '
    ```


Check the shell

``` { .sh .copy .select linenums="0" title="" }
$ echo $SHELL
/usr/bin/bash
```

Check Python version

``` { .sh .copy .select linenums="0" title="" }
$ python --version
Python 3.12.5
```

Check git version

``` { .sh .copy .select linenums="0" title="" }
$ git --version
git version 2.46.0
```

GitHub account

``` sh linenums="0" title=""
$ ssh git@github.com
Hi fdiblen! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```

**Useful Links:**

- To create a new account: [https://github.com/signup](https://github.com/signup)
- To connect to GitHub with SSH: [https://docs.github.com/en/authentication/connecting-to-github-with-ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---
## :watch: 14:35 (10 mins) - Create a Python package using a minimum profile

Install copier

``` { .sh .copy .select linenums="0" title="" }
python3 -m pip install --user pipx
python3 -m pipx ensurepath
pipx install copier
```

!!! info

    We will create a package called `baklava`


Create a new package by running:

``` { .sh .copy .select linenums="0" title="" }
copier copy https://github.com/nlesc/python-template.git baklava
```

Answer the questions as shown below:

```
Thanks for generating a project using our template.

You'll be asked a series of questions whose answers will be used to
generate a tailored project for you.

For each question there is a placeholder. Make sure you provide an
input to each of them.

🎤 Select a profile
   Minimum (bare minimum, no extra features)
🎤 Enter the name of the Python package.
   baklava
🎤 Enter the version of the Python package
   0.1.0
🎤 Enter your full name
   Faruk D
🎤 license
   Apache License, Version 2.0
🎤 Short description of package
   A sweet package
🎤 Add keywords to make your package findable on PyPI
   sweet,dessert
🎤 Enter the name of your GitHub username or organization
   fdiblen
🎤 What is your email address?
   f.diblen@esciencecenter.nl
🎤 Who is the copyright holder (the default is your full name)?
   Faruk D

Copying from template version None
    create  .
    create  NOTICE
    create  src
    create  src/baklava
    create  src/baklava/__init__.py
    create  src/baklava/my_module.py
    create  .copier-answers.yml
    create  MANIFEST.in
    create  README.md
    create  LICENSE
    create  .gitignore
    create  project_setup.md
    create  pyproject.toml

Your project "baklava" has been successfully created in baklava folder!

```

Run the command below to see a list of generated files:

```
tree -a baklava
```

Output:

```
├── .copier-answers.yml
├── .gitignore
├── LICENSE
├── MANIFEST.in
├── NOTICE
├── project_setup.md
├── pyproject.toml
├── README.md
└── src
    └── baklava
        ├── __init__.py
        └── my_module.py
```

Follow the next steps: Initialize a git repository:

```
cd baklava
git init
git add --all
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:fdiblen/baklava.git
```

<!-- ---
## :watch: 14:45 (5 mins) - Explain the generated files with minimum profile
 -->

---
## :watch: 14:50 (20 mins) - Update the new Python package

Add new features to the created package

``` { .sh .copy .select linenums="0" title="" }
cd baklava
copier update
```

Select all the features:

```
Thanks for updating your project using our template.

You'll be asked a series of questions whose answers are pre-populated
with previously entered values. Feel free to change them as needed.

Updating to template version 0.6.0.post19.dev0+bfb33bd
🎤 Select a profile
   Let me choose (decide each feature yourself)
🎤 Enter the name of the Python package
   baklava
🎤 Enter the version of the Python package
   0.1.0
🎤 Enter your full name
   Faruk D
🎤 Select a license (see: https://choosealicense.com)
   Apache License, Version 2.0
🎤 Who is the copyright holder (default: full name)?
   Faruk D
🎤 Short description of package
   A Sweet package
🎤 Add keywords to make your package findable on PyPI (comma-separated)
   keyword1,keyword 2
🎤 Enter the name of your GitHub username or organization
   fdiblen
🎤 What is your email address?
   faruk@universe.com
🎤 Select code quality features
   done (6 selections)
🎤 Select GitHub Action workflows
   done (2 selections)
🎤 Select publish and release features
   done (3 selections)
🎤 Select citation features
   done (2 selections)
🎤 Select documentation features
   done (4 selections)
🎤 Select community features
   done (2 selections)
🎤 What is the email address to report code of conduct violations?
   faruk@universe.com
Your project "baklava" has been updated successfully!
In case there are any conflicts, please resolve them. Then,
you're done.
```

Add the new files to the git repository:

```
git add --all
git commit -m"added new features"
```

---
## :watch: 15:10 (10 mins) - Create a new GitHub repository

Go to: [https://github.com/new](https://github.com/new)

- Repo name: baklava
- Description: `sweet Python package`
- Type: Public
- **NO README**
- **NO .gitignore**
- **NO license**


---
## :watch: 15:20 (15 mins) - Push the package to the new GitHub repository

Push to GitHub:

```
git push --set-upstream origin main
```

- Look at the generated `next steps` issues
- Look at the GitHub Action workflows


---
## :watch: 15:35 (10 mins) -  Feedback session

Short link: [https://tinyurl.com/rsecon24pt](https://tinyurl.com/rsecon24pt)

Long link: [https://hackmd.io/@pBkWTvQwSa6d52OQUwKE6g/BktUdXQ20](https://hackmd.io/@pBkWTvQwSa6d52OQUwKE6g/BktUdXQ20)

Questions:

- What features did you like the most?
- What features need to be improved?
- What features would you like to be added?
- Any other suggestions or notes?



## Tips

### using ruff to format your code

```
cd baklava/
python -m venv venv
. ./venv/bin/activate.fish
python -m pip install --upgrade pip setuptools
python -m pip install .[dev,publishing]
ruff format
```


## FAILING

Competing workflows
CFF date