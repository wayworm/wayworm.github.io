---
creation date: 2025-07-03 21:03
modification date: Thursday 3rd July 2025 21:03:04
math: true
categories:
  - projects
  - project-notes
tags: 
title: LifeMap
---


**Technologies:**  Python, Flask, SQLite, HTML, CSS, JavaScript, Jinja2, Bootstrap, Font Awesome

**Role:**  Developer, Researcher


LifeMap is a Flask-based web application for managing personal projects and hierarchical tasks. Users can register, log in, create new projects, and organize tasks and subtasks within those projects.

#### Features
- ##### User Authentication:

	- User registration with password hashing.
	- User login and session management.
	- Password change functionality.

- ##### Project Management:

	- Create new projects with title, description, start date, and due date.
	- View a list of all owned projects.
	- Edit project titles. 

- ##### Task Management:

	- Hierarchical task structure (subtasks)
	- Add, edit, and delete tasks and subtasks.
	- Input fields for task name, description, due date, and planned hours.
	- Dynamic addition and deletion of tasks/subtasks without page refresh.
	- Visual indication of task hierarchy using indentation and color coding.
	- Collapse/expand subtask lists.

- ##### Database:

	- SQLite database (LifeMap.db) for storing user, project, and task data.

- ##### Responsive Design:

	- Utilises Bootstrap 5 and Font Awesome for styling and icons.
	- Includes custom CSS for enhanced aesthetics.

