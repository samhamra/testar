# Commons Android app

## Project
Name: Wikimedia Commons Android app
[GitHub repository](https://github.com/commons-app/apps-android-commons)

## Project description and Android overview
The Wikimedia Commons Android app is an application that is used to upload images, sounds and other media files to the Wikimedia Commons repository. Files uploaded to the repository can then further be used across all Wikimedia projects such as Wikipedia, WikiBooks, Wikinews and more. The purpose of the Commons repository is to:
> "provide a media file repository that makes available public domain and freely-licensed educational media content to all, and that acts as a common repository for the various projects of the Wikimedia Foundation.[<sup>[1]</sup>](#sources)

Now the Android app is a tool to help simplify the uploading process by using their Android phones/tablets to quickly upload their files. It was originally founded by the Wikimedia Foundation but is now managed and maintained by grantees and volunteers of the Wikimedia community as an open-source project.[<sup>[2]</sup>](#sources)

Generally Android applications are built using a set of components, there are many, but here we will go through some of the most important ones. [<sup>[3]</sup>](#sources)

**Activities** serve as a user’s entry point to the application, the activity class creates a user window where UI elements can be placed. [<sup>[4]</sup>](#sources)

**Fragments** represent a portion of the UI in an activity, you can view it sort of like a sub activity. A fragment is always embedded inside an activity.[<sup>[5]</sup>](#sources)

**Layouts** define the visual structure of the an application, such as user interface elements for an activity. Android allows for two ways of declaring layouts, either by providing an XML structure using androids XML vocabulary, or instantiating the layout elements at runtime using the View and ViewGroup classes provided in the android SDK.[<sup>[6]</sup>](#sources)

**Services** are components which can perform long-running operations without providing a user interface, and can run both in the foreground and background. Examples include playing music, performing interprocess communication, file I/O and more.[<sup>[7]</sup>](#sources)

**Intents** are messaging objects that can be used to request actions from other app components, such as starting activities, services or broadcasting messages to other applications.[<sup>[8]</sup>](#sources)

This particular Android application is written in Java using the Android SDK.

## Project architecture 
Firstly, the major separation of code lies in separating data, layouts and graphics from the logic. All of the res(ources) lie under /app/src/main/res/, this includes layouts, graphics and other data such as textual strings translated into a larger number of different languages as this is a globally used application. Pretty much the rest of the codebase, that is, activities, fragments, services, intents, widgets and more are written in Java and located under  /app/src/main/java/fr/free/nrw/commons/.

### [/app/src/main/java/fr/free/nrw/commons/](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/)

[**/auth**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons//auth)

Android account integration, Commons account creation and login including two-factor authentication. Also includes authentication session management. Contains both the activities and background logic to fulfill this. 

[**/caching**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/caching)

Cache controller that currently is used for categories and location. 

[**/category**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/category)

Categories are a way to tag uploaded media. This directory includes the logic behind a category, the activity to display category suggestions and provide category selection to the user. Also provides code to interact with the local database of media relevant to categories. 

[**/contributions**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/contributions)

The internal handling and representations of the uploaded data, includes storage and synchronization between Commons and the android app. Also includes the activities of displaying a list of contributions by the user.

[**/data**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons//data)

Contains a class that provides a couple additional helper functions for SQLite database used by the application. 

[**/di**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons//di)

Includes code to streamline to use of the Dagger 2 library. [Dagger 2](https://github.com/google/dagger) is a Google made library used for compile-time approach to dependency injection. 

[**/location**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/location)

Handling of fetching, displaying and updating the user's location using the device's built-in GPS provider.

[**/media**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/media)

Contains the activity and user facing code to display a specific contribution including the picture and details about that contribution.

[**/modifications**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/modifications)

A "Modification" is the internal representation of a change to an existing upload, includes storage and synchronization code, similar to contributions handling.

[**/mwapi**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/mwapi)

Communication with the Commons Mediawiki API and Event Logging APIs. For example authentication, data fetching, uploading, modifying and much more.

[**/nearby**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/nearby)

Handling of the "Places nearby" feature, Wikidata Query Service. Includes both the user facing activity and background code to display “nearby” places. 

[**/settings**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/settings)

Handling of "Settings" feature, primarily the settings activity and display of current users settings. 

[**/theme**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/theme)

Application allows for theme changes, that logic lies here. Also includes code for navigation.

[**/ui/widget**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/widget)

Includes widgets and fragments used by for example the "Places nearby" feature, as well as displaying html with links and backward compatible textual representations.

[**/upload**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/uploader)

Contains data upload logic. This includes both the user facing activity and the logic of calling appropriate functions for preparation of data and handling of Android api for file selection. 

[**/utils**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/utils)

Various utilities. Includes functionality from Android related utilities to date formats. 

### [/apps-android-commons/tree/master/app/src/main/res/](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/res)

[**/drawable**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/res/drawable)

Contains all the images displayed in the application. This includes the drawable-xxxx folders for different sized screens.

[**/layout**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/res/layout)

This folder contains the XML files for the structure of various screens the user can see. 


## Selected issues

**Title:** Fix Lint errors/warnings

**URL:** https://github.com/commons-app/apps-android-commons/issues/171

**Summary:** The project contained some hundred lint warnings and errors, we only felt a subset of those were actually doable/useful.

**Title:** Tech-improvement: Use Glide for image loading / caching

**URL:** https://github.com/commons-app/apps-android-commons/issues/889

**Summary:** The project uses an asynchronous class to load and cache images for display to the user. The issue requests that this is replaced with the Glide library, which is a more advanced and Google supported image loading library. 

**Title:** Tech-improvement: JSON based Wikimedia API

**URL:** https://github.com/commons-app/apps-android-commons/issues/885

**Summary:** Replace the current XML approach to Wikimedia API calls, which is deprecated, to the supported JSON format. 

## Onboarding experience
When we started working on the project, there was a build issue with the translated string values in the app. This was a result of improper naming of the North Korean variant of the Korean language translation. Reading into the Android documentation on string translation, the proper name was identified and pointed out in an issue post on Github and a pull request fixing the problem. After a couple days that pull request was accepted and merged into the official repository. In the meantime, the group members of this assignment applied the fix in order to continue working on refactoring. 

## Requirements affected by functionality being refactored
**Lint errors:** Working on the Lint issue resulted in a lot of small changes to many different requirements and files. Most of the warnings only required smaller changes to the source code, like typography changes to translation strings. Other warnings required moving away from deprecated or error-prone code. The largest amount of time was spent on warnings and errors that required a broad understanding of the program. This is due to certain errors being false positives and we did not want to break the program by following the lint errors completely. The final type of error we generally felt like we didn’t have enough knowledge to attempt were those that affected security, as they required larger overhauls of the application.

The functionality that was affected by our refactoring:
- Management of contributions made by the user
  - Displaying details of a contribution to a user
  - Management of stored contributions
  - Changes to custom imageview object for displaying contributions
  - User facing upload activity changes 
  - Parsing function of local contributions
- User facing and background aspects of logging in
- Various changes to translation files
- Modification of class that loads components and injects dependencies
- General utility functions
- Nearby points of interest 
- Categories list for user
- View Styles

**Glide:** This refactoring required changes to the version of Android being used and adding Glide to the dependency list. The changes to the code base itself was in Contributions and Media. Specifically, the java and xml code related to displaying all contributions made by the user and the detailed view of a single contribution. 
**Use JSON for api calls:** 
No actual refactoring was done for this issue because of time limitations. Having spent some time looking into the issue, we came up with a roadmap:
The MediaWikiApi interface needs to be reimplemented using the OkHttp client (as suggested by the user ‘psh’ in the issue thread). It seems much of the logic in ApacheHttpClientMediaWikiApi can be reused which makes this simpler. The new class could be called ‘OkHttpClientMediaWikiApi’. The provideMediaWikiApi function in CommonsApplicationModule needs to be changed to use this new class instead of the old ApacheHttpClientMediaWikiApi.


Even though much can be reused, the MWApi class used in ApacheHttpClientMediaWikiApi needs to be replaced with a class that uses the JSON MediaWiki API in this new implementation of the MediaWikiApi. This new class should support the following:

a. Validating login
b. Getting an edit token
c. Sending post/get requests with parameters
d. Uploading files
e. Setting/getting auth cookie
f. Keeping login state


New tests need to be written for the new MediaWikiApi implementation. Like for ApacheHttpClientMediaWikiApi, much code can be reused from ApacheHttpClientMediaWikiApiTest with some minor changes (e.g. changing tests that use xml to use json instead).
## Existing test cases relating to refactored code
This project almost completely lacks UI tests, and most of our lint fixes were connected to the UI, therefor the refactored code were mostly lacking tests, excluding for example the changes to move from commit() to update() in the SettingsActivity is tested in the SettingsActivityTest.
The CommonsApplicationTest is unfortunately unfinished and could potentially be something we could work with on assignment 4.
The original image loader was lacking tests, so the new implementation also does not include tests. This is due to the code mainly relying on libraries and other code in the program that is separately tested.
The upgrade to the JSON MediaWikiAPI implementation would also requires testcode, the current API is covered by many tests.

## The refactoring carried out
(Link to) a UML diagram and its description

## Test logs
Overall results with link to a copy of the logs (before/after refactoring).
The refactoring itself is documented by the git log.

## Updates to the source (For P+ #4)
When we first started working on the project we coincidently came in when a bad commit was merged into the master. The issue had to do with the naming convention in Android for string translations. Despite it being a roadblock for the main refactoring portion of the assignment, it gave us a good opportunity to learn about the Android documentation and the way the the team working on the project handled issues and pull requests. Once that was out of the way our group split up the refactoring into two main portions: minor changes throughout the project and one major overhaul of a feature.

Working on the many minor changes we used the repositories [Codacy](https://www.codacy.com/) page and Android Studio’s built in code analyzer. The types of errors that were displayed varied from risky variable declaration, deprecated api usage to static field leakage. These kind of changes had very little effect on the overall architecture of the software project because they are mainly small improvements or fixes. Where this kind of refactoring is helpful is improvements to the softwares reliability and future usability. Despite being small in size, these changes can still be risky because a code analyzer isn’t an all powerful tool. Some of the errors that were output are decisions made for a reason that if changed would cause the program not to work correctly. So working on each individual issue lead to a lot of time reading and analyzing the surrounding code a design to fully understand a potential change and its impact. 

Moving onto the larger refactor it was time to use what we had learned about the project architecture and replace a major component of the program. The feature we were working on here was to implement Glide for loading of images instead of the current inefficient method. In a very simple application implementing this change would only take a few lines of code and some dependency changes. For a project of this size and complexity, more time is needed to ensure the changes match the style and design patterns used. For example, the original code used a custom image viewer object that loaded images with an async object. Because of this the new code followed a similar design, requiring a new custom image viewer object and new code to load the image. The extra time put into this implementation will allow new and existing contributors to understand the architecture because it is consistent with how it was before.

Through these two types of changes we have implemented we as a group have worked on the two ends of the refactoring spectrum, large scale changes and minor fixes. Each of these required knowledge of general programming practices and specific understanding of the repositories design.  

## Benefits, drawbacks, and limitations of refactoring (For P+ #6)
When we write code we know the problem at hand and have a good understanding of what our code is trying to achieve. However other people may find it difficult to understand the problem going from the code, if for example there is a bug in our logic. Therefor we need to write clear code and comment it well, write code that relates to some requirement of the program and make sure it is tested to those requirements and the functionality implemented. The most obvious benefits to refactoring are better code quality. Code that gets reviewed multiple times by different people tends to become more readable and contain less bugs. Going back and reviewing old code can also help speed up processes and help with the longevity of the code base, which was what we focused on with the issues we picked/created. 

We focused on three different aspects of refactoring optimising the code, updating deprecated components, and cleaning the code. The biggest optimisation aspect was replacing the current image loader component with a more reliable one as requested by an open issue in the repo (#889). Gilde is an image loader put out by Google and is a generally recommended solution. When working on the replacement we found an issue with how the programm stores image urls and submitted an issue to the repo (#1169). The image loader issue is a great example of the benefits and drawbacks that can arise from refactoring. On one hand we are improving the final product by replacing the image loader and found a bug that had not been discovered yet, but on the other we are changing functionality that works by implementing this new thing, we might create more bugs, as the saying goes “if it ain’t broke don’t fix it”. We spent some time cleaning the codebase as many lint warnings and errors were noted in one of the open issues (#171), we helped fix text formatting, code imports, style warnings and code comments. This part of refactoring is often overlooked since it is not the most exciting, but will help keep the codebase clean and definitely helps with readability, however without broad knowledge of the code base we might be affecting things that ought to be the way they are despite causing some sort of warning or error in the linting/analysis of the code.

## Effort spent

| Name | Planning | Reading Doc | Setup | analyzing code/output | Writing Doc/Report  |  Writing Code | Testing |
| -	 | -	 | -	 | -	 | -	 | -	 | -	 | -	 |
|Jon	|4.5	|2	|3	|3.5	|6	|3	|2.5	|
|Sam	| 4	| 3	|    3	|     2	|   8	|  5	| 1	|
|Johan	| 4	| 3	| 2	| 6	| 5	| 4	| 1	|
|Masaki	|4	|1	|2	|2	|1 	|1	|3	|
|Hampus	|4	|6	|2	|4	|5	|4	|3	|

## Overall experience
Each group member shared some insight into how they felt after the assignment:
**Jón:** I guess the biggest takeaway for me was the fact that it is not as hard as it might seem to contribute to the open source community. I had in the past looked at some projects in my field of interest but always shied away from contributing to them, this assignment changed my view on that and I intend to take a second stab at some of the projects I had looked at in the past.

**Sam:** It’s easier to make good refactoring changes if you have good communication with the rest of the development team, to make sure your changes is valid/correct and useful. Aswell, having a good understanding of the project, structure and architecture could be extremely time-saving when working with some issues. Also, I thought this project was lacking a lot of in-source documentation. I for one also learned some basic Android, project setup, project build, language basics etc.

**Johan:** I got to practice getting into a decently sized codebase that is not too well documented. I’m used to just being able to google most stuff to find documentation, but in this project I had to figure most things out by looking at the source code. I also realized that there are many more ways to contribute to an open source project than just writing code, e.g. documentation, roadmaps etc.

**Masaki:** I learned basic commands of git. Such as see what’s  changes ‘git status’ add things to be committed ‘git add .’ commit ‘git commit -m “change name” ‘ push to github ‘ git push origin head’.

**Hampus:** Before working on this project I had a fair bit of experience working on Android so I was able to focus on learning the architecture and design patterns of the project. I had never worked on a project larger than a couple people so this was a good opportunity to understand large scale Android projects. Looking at other repositories can often be intimidating, but with my updated understanding of git and coding practices, contributing to the project was a lot easier than I expected. There have been a few projects I have looked into in the past and not contributed to, after this course I think I will go back and see if there is anything I can update. 

## Links to accepted pull requests
https://github.com/commons-app/apps-android-commons/pull/1161
https://github.com/commons-app/apps-android-commons/pull/1136


 <a id="sources">Sources:</a>

[1]https://commons.wikimedia.org/wiki/Commons:Project_scope#Aim_of_Wikimedia_Commons
[2]https://github.com/commons-app/apps-android-commons/blob/master/README.md
[3]https://developer.android.com/guide/components/index.html
[4]https://developer.android.com/guide/components/activities/index.html
[5]https://developer.android.com/guide/components/fragments.html
[6]https://developer.android.com/guide/topics/ui/declaring-layout.html
[7]https://developer.android.com/guide/components/services.html
[8]https://developer.android.com/guide/components/intents-filters.html
