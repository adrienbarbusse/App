ASSERTIONS
==========

**Author**: Juan Peist juan@john.cat

**Last update**: January 22th 2018

Vocabulary / Index
------------------

[**APP**](#app): All the app, including all modules, the blog section, user profile, login and sign in logic, etc.

[**PROFILE**](#profile): All the user data and options.

[**BLOG**](#blog): Entries from medium.com.

[**MODULE**](#modyle): Course. It consists of a distributive page with active an non active sessions. The only one in the v1.0 is "STOP SMOKING".

[**SESSION**](#sessions): Chapters of the module. It consists of screens.

[**SCREEN**](#screens): The content unit. It consists of text, animations and UI. For now there are 3 types of screens: QA screens, slideshow screens and date screens.


App
---

+ The app can have infinite modules.

Profile
-------

+ The profile is composed of general fields (name, age, email, notifications settings, etc) and specific profile to each user/module (from now on "module profile").

+ The user can modify the general fields.

+ The user can not see or modify a module profile. These are modified depending on the user's interactions in the sessions.


Blog
----

TODO: develop tag / profile filter system assertions.


Module
------

+ A module can have infinite sessions.

+ A module is accesible from the dashboard page.

+ A module can be reset from the user's profile.

+ When the user reset the module all the data associeted with the module is deleted.


Sessions
--------

+ A session can be active (ready to be consumed by the user) or not active (the user must first consume previous sessions to transform a non-active session into active).

+ The user must finish the first session to have access to the second one and so on.

+ If the user didnt finish the session, the session is not complete and the next time they start the the module the session start again.

+ The session is recorded as complete only if the user finishes it.

+ All sessions have an "END" screen. If the user does not give "OK" to the end screen the session is not recorded.

+ At the end of the session the user is redirected to the dashboard.


Screens
-------

+ The screens can be of four types
  1. QA
  2. Number
  3. Date
  4. Slideshow

+ Each screen can be shown or not to the current user depending on the module profile.

+ QA screens can have from 1 to 4 interactions buttons.

+ In QA screens interaction button advance to another screen, this screen could be unique or two or more buttons can advance to the same screen.

+ Number, date and slideshow screens always advance to a unique screen without depending on the type of response.

+ Slideshow screens can contain 2 to 4 slides.

+ The last slide of a slideshow always has an OK button. 

  :exclamation: **Alert**: The user can get stuck in the slideshow by not advancing until the last slide. 

  :exclamation: **Possible Solution**: Slideshow auto play or CLOSE button on all slides.

+ Each screen contains:
  1. Title: Required. Max characters limition. Default: no
  2. Body text: Optional. Max characters limitation. Default: no
  3. Image: Optional. Gif animado. Default: no
  4. UI: Optional. Button/s, date or number fields. Default: "OK" button.

+ Each slide of the slideshow contains:
  1. Title: Required. Max characters limition.
  2. Body text: Optional. Max characters limitation.
  3. Image: Optional. Gif animado.
  4. Close button. 

+ Some user interactions can add/delete/modify fields in the module profile.

+ A user interaction that changes a field in the module profile restart the actual session or the complete module. 

+ A user interaction that changes a field in the module profile shows a dead-end screen with a message and an OK button that redirects to the session first screen or the first screen of the first session.

:exclamation: **Alert**: In the actual wireframe version the only screen "wrong" with the past statements is "NRT No 2".
