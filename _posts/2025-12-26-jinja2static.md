---
title: Jinja2Static
tags: Jinja2 Static-File-Server
---

While learning to develop frontend applications in the late 2010's, I decided to code up my [resume](michaelairola.com) only using Javsacript.

This project was a really fun new-to-sofwtare-engineering project. I learned a lot of helpful things about Javascript and the current frontend-ecosystem. Unfortunately, as my experience has changed and the configurability of my portfolio has become a priority, the Javascript implementation became less ideal for updating and revising my resume. This being the case, I decided to refactor my resume to be a static site that solely uses HTML and CSS. 

In order to make updating my resume as easy as possible, I wanted to use a simple templating language for building. As an added bonus, the developer environment would ideally have the ability to run a localhost server that monitored file changes and updated the build accordingly. These features can be found in plenty of software development frameworks (jekyll, flask, etc), however they are all more robust than what i need for this small use-case. This led to creating a new and simple python package - [Jinja2Static](https://pypi.org/project/jinja2static/).

# Jinja2

As far as simple templating languages go, Jinja2 is my favorite. Python is such an easy programming language to use, and Jinja2 happens to be one of the most common templating languages in the industry. For example, both the [Flask](https://flask.palletsprojects.com/en/stable/) and [Django](https://www.djangoproject.com/) frameworks use it under the hood. Because of this, Jinja2 was the natural choice for a tool that could build. 

# Configurability

For this simple use-case, we only need a couple of configuration options. I decided to be PEP-compliant and have the tool check for these configurations using a `pyproject.toml` file (specifically in the `[tools][jinja2static]` location): 

- templates : This is the templates directory where all templates can be found. Defaults to "./templates" directory. 
- static : This is the static directory that all static files can be found. Defaults to "./static" directory.
- pages : This is a list of template files that should be built for. Defaults to "index.html".

Very simple! 

Easy to setup, and no crazy boilerplate code that will be confusing and unnecessary. 

# The build process 

Take, for example my resume (code)[https://github.com/michaelairola/resume] - all you would have to do to build is: 

```
    pip install jinja2static && jinja2static build
```


# Developer Server
To run the development server:

```
    jinja2static dev
```

The above was super fun to create. Making an async localhost server work well with file-update checkers and incremental builders came with a set of problems that were really fun to create solutions for.

For suggestions on new features or bugfixes to the, feel free to email me with ideas :)  

