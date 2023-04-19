---
title: "Project 0 Project Manager Part 2"
description: ""
excerpt: ""
date: 2021-06-04T16:43:17+05:30
lastmod: 2021-06-04T16:43:17+05:30
draft: false
weight: 50
images: ["Cover.png"]
categories: []
tags: []
contributors: []
pinned: false
homepage: false
---

In the last part of the blog post, we set up the basic GUI app with all the different buttons but we did not add any functionality. 

Now, we are going to add the functionality to the project manager application. To do this, we need to add a way to store data like the description, changelog, etc. of each project. The best way to store data is by using JSON files.

A simple JSON document could look like this:

```json
{
    "Name": "Satwik",
    "Interests": [
        "Artificial Intelligence",
        "Puzzles"
    ],
    "Id": 1234,
    "Contact Info": {
        "Github": "https://github.com/code-explorer",
        "Blog": "https://satwikkambham.blogspot.com"
    }
}
```

A JSON file contains either an array (if the file starts and ends with []) or an object (if the file starts and ends with {}). In the above example, the JSON file contains an object in which Name, Interests, Id and Contact Info are the keys with the respective string, array, integer, and object as their values.

This format allows us to easily read and write necessary info into a file. To read more about JSON files refer to the following link: [JSON Wikipedia](https://en.wikipedia.org/wiki/JSON) and use this link to find out how you can use JSON in your chosen programming language: [List of libraries which allow parsing of JSON data](https://www.json.org/json-en.html).

For my project, I am going to make a hidden directory in the folder containing my projects and store my JSON files for each project in the hidden directory. For each of my projects the JSON files are going to look like this:

```json
{
    "Name": "Project Name",
    "Description": "This is the project description which will contain some basic information about the project.",
    "Status": "On Going",
    "Tags": [
        "C++",
        "Qt",
        ""
    ],
    "IDE": "code ..\\Project Name",
    "Exe": "..\\Project Name.exe",
    "Github": "https://github.com/code-explorer",
    "To do list": [
        "Add idea 3",
        "Add idea 4",
        "Add idea 5"
    ],
    "Changelog": [
        "Added idea 1",
        "Added idea 2"
    ],
    "Screenshot": "..\\Project Name.png"
}
```

I am going to store the following:
- Project Name
- Project Description
- Project Status
- Project Tags
- Command to open the project in relevant IDE
- Path to executable
- Github repository link
- To-do list
- Changelog
- Path to a screenshot of the project
- with more added as necessary...

To implement this into the code, first, we detect whenever a project is selected from the list. If a project is selected from the list, we find the appropriate JSON file and display the contents to the screen. If the JSON file is not present for that project, then we create a JSON file.

![Phase 1](https://1.bp.blogspot.com/-rIAPoT0K30U/YJzuh5OoFcI/AAAAAAAAAA8/5focWuU3oQwL5QUobBZm1Y9b1mIskCbLACLcBGAsYHQ/s1370/1.gif)

The next step is adding the to-do list and changelog functionality. 

![Phase 2](https://1.bp.blogspot.com/-OGzjg0bK7UQ/YKepMNKsHXI/AAAAAAAAABE/lIkAX_YRAnw8GRB6-vcaF6TcctAY9z5AwCLcBGAsYHQ/s1370/3.gif)

The status button functionality has been added, allowing us to change the current status of the project. Also the open in IDE, run executable and open Github repository buttons have been implemented so that whenever a button is pressed, a suitable command is executed in the terminal. For example, I am using the VSCode IDE which can be opened from the terminal by running the "code" command. The Github repository can also be opened in a web browser through the terminal.

Lastly, I will add the ability to create new projects and edit an existing project.

![Phase 3](https://1.bp.blogspot.com/-dOa9QRSPSuA/YKeqzI3s_KI/AAAAAAAAABU/aqUUa9l4L-4s_h4OYKsacszkwx4XQ-qEACLcBGAsYHQ/s1370/4.gif)

This mostly sums up the project. In the future, I am going to add more functionality as needed. You can find the source code of the project at [my Github repository](https://github.com/code-explorer/Project-Manager).
