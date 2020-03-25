# Android Table of Elements

A collection of ordered subjects and curated tutorials for learning Android development.

## Local Development

To develop the site locally use:

```npm run build -- --watch```

## Deployment

Auto deploys when merging to master.

## Content

The table of elements is composed of sections and subjects.

**Section:** A section is a grouping of subjects and represents an area of Android development eg. *Programming Language*, *User Interface* or *Networking*. Every section has a base color. The base color and it’s shades are used to define the subjects within a section (see the Color Guide at the end for more details).

![alt text](https://raw.githubusercontent.com/razeware/einstein/master/javascript/images/sections.png "")

**Subject:** Subjects represent a well-defined topic of Android development eg. *Kotlin*, *RecyclerView* or *Firebase*. Subjects are organised from left to right.

![alt text](https://raw.githubusercontent.com/razeware/einstein/master/javascript/images/subjects.png "")

In sections with more than 4 subjects. Subjects that are closely-related should be organised vertically in a column to create a sub-section eg. *Material Design*, *Custom Fonts* and *Drawables* are all related to UI styling.

![alt text](https://raw.githubusercontent.com/razeware/einstein/master/javascript/images/sub-sections.png "")

## Configuring the Table of Elements

The table of elements is built on a 5 column square grid.

![alt text](https://raw.githubusercontent.com/razeware/einstein/master/javascript/images/grid.png "")

Squares on the grid are configurable through JSON objects. JSON configuration for the table: ```/src/data/content.json```

Objects are displayed on the grid according to their object number.

To see the JSON object number of every square, use the grid-mode view when configuring content locally ```/grid.html```.

An object can have the following attributes:

```
{
  "elementClass": "",
  "elementSection": "",
  "elementName": "",
  "elementCode": "",
  "elementDescription": ""
  "elementTutorials": [ [“”, ””] ]
}

//elementClass: Classes to adapt a square for a section, subject or fill (String)
//elementSection: Anchor for a section (String)
//elementName: Display name of a section or subject (String)
//elementCode: Code in the corner of a subject (String)
//elementDescription: Description of a subject (String)
//elementTutorials: Subject tutorials and links eg. Articles, Video Courses, Books (Array)

```

There are three types of elements that can be placed on the grid squares:

* Section
* Subject
* Fill/Empty

An explanation and example object configuration for each element is as follows:

```
Section: Define the start of a group of subjects

{
  "elementClass": "light-green-1",
  "elementSection": "section-1",
  "elementName": "Programming"
}
```

```
Subject: Define a subject

{
  "elementClass": "light-green-1",
  "elementName": "Kotlin",
  "elementCode": "Kn",
  "elementDescription": "...",
  "elementTutorials": [
    [“Programming in Kotlin (Article)”, “https://www.raywenderlich.com/...”],
    [“Programming in Kotlin (Video Course)”, “https://www.raywenderlich.com/...”]
  ]
}
```

```
Fill/Empty: Fill up empty squares at the end of a row with fill (background) or empty (no background)

{
  "elementClass": "fill",
}

{
  "elementClass": "empty",
}

```

## Color Guide

Sections and subjects on the grid are colored through special classes. To create harmony between sections, organise them vertically according to the color wheel. You can use the color page to quickly reference color class names ```/colors.html```.

![alt text](https://raw.githubusercontent.com/razeware/einstein/master/javascript/images/colors.png "")

When choosing a base color for a section start with the left-most shade. The section name and first column of subjects use the base color. Subsequent columns of subjects use the next shade of the base color. The color classes are added to the ```elementClass``` of an object. Classes color the text for the section and the background of the subject square.





