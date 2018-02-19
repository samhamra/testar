# Commons Android app

## Project
Name: Wikimedia Commons Android app
[GitHub repository](https://github.com/commons-app/apps-android-commons)

## Project description and architecture
The Wikimedia Commons Android app is an application that is used to upload images, sounds and other media files to the Wikimedia Commons repository. Files uploaded to the repository can then further be used across all Wikimedia projects such as Wikipedia, WikiBooks, Wikinews and more. The purpose of the Commons repository is to:
> "provide a media file repository that makes available public domain and freely-licensed educational media content to all, and that acts as a common repository for the various projects of the Wikimedia Foundation."[<sup>[1]</sup>](#sources)

Now the Android app is a tool to help simplify the uploading process by using their Android phones/tablets to quickly upload their files. It was originally founded by the Wikimedia Foundation but is now managed and maintained by grantees and volunteers of the Wikimedia community as an open-source project.[<sup>[2]</sup>](#sources)

Generally Android applications are built using a set of components, there are many, but here we will go through some of the most important ones. [<sup>[3]</sup>](#sources)

**Activities** serve as a user’s entry point to the application, the activity class creates a user window where UI elements can be placed. [<sup>[4]</sup>](#sources)

**Fragments** represent a portion of the UI in an activity, you can view it sort of like a sub activity. A fragment is always embedded inside an activity.[<sup>[5]</sup>](#sources)

**Layouts** define the visual structure of the an application, such as user interface elements for an activity. Android allows for two ways of declaring layouts, either by providing an XML structure using androids XML vocabulary, or instantiating the layout elements at runtime using the View and ViewGroup classes provided in the android SDK.[<sup>[6]</sup>](#sources)

**Services** are components which can perform long-running operations without providing a user interface, and can run both in the foreground and background. Examples include playing music, performing interprocess communication, file I/O and more.[<sup>[7]</sup>](#sources)

**Intents** are messaging objects that can be used to request actions from other app components, such as starting activities, services or broadcasting messages to other applications.[<sup>[8]</sup>](#sources)

This particular Android application is written in Java using the Android SDK.

Firstly, the major separation of code lies in separating data, layouts and graphics from the logic. All of the res(ources) lie under /app/src/main/res/, this includes layouts, graphics and other data such as textual strings translated into a larger number of different languages as this is a globally used application. Pretty much the rest of the codebase, that is, activities, fragments, services, intents, widgets and more are written in Java and located under  /app/src/main/java/fr/free/nrw/commons/.

The Java logic is separated even further into a set of areas, as documented in the [repository documentation](https://github.com/commons-app/apps-android-commons/wiki/Technical-Overview):
### [/app/src/main/java/fr/free/nrw/commons/](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/)

[**/auth**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons//auth)

Android account integration, Commons account creation and login including two-factor authentication. Also includes authentication session management.

[**/caching**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/caching)

Unfinished general caching controller

[**/category**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/category)

Everything about Categories

[**/contributions**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/contributions)

The internal handling and representations of the uploaded data, includes storage and synchronization between Commons and the android app.

[**/data**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons//data)

Perhaps obsolete database helper

[**/location**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/location)

Handling of fetching, displaying and updating the user's location using the device's built-in GPS provider.

[**/media**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/media)

Upload/Picture detail view

[**/modifications**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/modifications)

A "Modification" is the internal representation of a change to an existing upload, includes storage and synchronization code, similar to contributions handling.

[**/mwapi**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/mwapi)

Communication with the Commons Mediawiki API and Event Logging APIs. For example authentication, data fetching, uploading, modifying and much more.

[**/nearby**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/nearby)

Handling of the "Places nearby" feature, Wikidata Query Service

[**/settings**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/settings)

Handling of "Settings" feature

[**/theme**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/theme)

Application allows for theme changes, that logic lies here. Also includes code for navigation.

[**/widget**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/widget)

Includes widgets and fragments used by for example the "Places nearby" feature, aswell as displaying html with links and backward compatible textual representations.

[**/uploader**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/uploader)

Contains data upload logic

[**/utils**](https://github.com/commons-app/apps-android-commons/tree/master/app/src/main/java/fr/free/nrw/commons/utils)

Various utilities




 <a id="sources">Sources:</a>

[1]https://commons.wikimedia.org/wiki/Commons:Project_scope#Aim_of_Wikimedia_Commons
[2]https://github.com/commons-app/apps-android-commons/blob/master/README.md
[3]https://developer.android.com/guide/components/index.html
[4]https://developer.android.com/guide/components/activities/index.html
[5]https://developer.android.com/guide/components/fragments.html
[6]https://developer.android.com/guide/topics/ui/declaring-layout.html
[7]https://developer.android.com/guide/components/services.html
[8]https://developer.android.com/guide/components/intents-filters.html


## Selected issues

**Title:** Fix Lint errors/warnings

**URL:** https://github.com/commons-app/apps-android-commons/issues/171

**Summary:** The project contained some hundred lint warnings and errors, the ones that we only felt a subset of those were actually doable.



**Title:** Tech-improvement: Use Glide for image loading / caching

**URL:** https://github.com/commons-app/apps-android-commons/issues/889

**Summary:** The project uses an asynchronous class to load and cache images for display to the user. The issue requests that this is replaced with the Glide library, which is a more advanced and Google supported image loading library.

**Title:** Tech-improvement: JSON based Wikimedia API

**URL:** https://github.com/commons-app/apps-android-commons/issues/885

**Summary:** Replace the current XML approach to Wikimedia API calls, which is deprecated, to the supported JSON format.

## Onboarding experience
When we started working on the project, there was a build issue with the translated string values in the app. This was a result of improper naming of the North Korean variant of the Korean language translation. Reading into the Android documentation on string translation, the proper name was identified and pointed out in an issue post on Github and a pull request fixing the problem. After a couple days that pull request was accepted and merged into the official repository. In the meantime, the group members of this assignment applied the fix in order to continue working on refactoring.

## Requirements affected by functionality being refactored
**Lint errors**
TODO: enter list here
**Glide:** This refactoring required changes to the version of Android being used and adding Glide to the dependency list. The changes to the code base itself was in Contributions and Media. Specifically, the java and xml code related to displaying all contributions made by the user and the detailed view of a single contribution.
## Existing test cases relating to refactored code

## The refactoring carried out
(Link to) a UML diagram and its description
## Test logs
Overall results with link to a copy of the logs (before/after
refactoring).
The refactoring itself is documented by the git log.
## Effort spent
For each team member, how much time was spent in
1.  plenary discussions/meetings;
2.  discussions within parts of the group;
3.  reading documentation;
4.  configuration;
5.  analyzing code/output;
6.  writing documentation;
7.  writing code;
8.  running code?

## Overall experience
What are your main take-aways from this project? What did you learn?
Is there something special you want to mention here

## Updates to the source (For P+ 4)

## Benefits, drawbacks, and limitations of refactoring (For P+ 6)


- Dashes work just as well
- And if you have sub points, put two spaces before the dash or star:
  - Like this
  - And this
