ASSERTIONS
==========

**Author**: Juan Peist juan@john.cat

**Last update**: January 22th 2018

Vocabulary / Index
------------------

[**APP**](#app): All the app, including all modules, the blog section, user profile, login and sign in logic, etc.

[**PROFILE**](#profile): All the user data and options.

[**BLOG**](#blog): Entries from medium.com.

[**MODULE**](#module): Course. It consists of a distributive page with active an non active sessions. The only one in the v1.0 is "STOP SMOKING".

[**SESSION**](#sessions): Chapters of the module. It consists of screens.

[**SCREEN**](#screens): The content unit. It consists of text, animations and UI. For now there are 3 types of screens: QA screens, slideshow screens and date screens.

[**TIPS**] 

[**SOS**] -> http://intercom.com


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

+ The first session always define the module profile.

+ The first session can not contain logics dependent on module profile.

+ A session can be active (ready to be consumed by the user) or not active (the user must first consume previous session to transform a non-active session into active).

+ The user must finish the first session to have access to the second one and so on.

+ A bussines logic can apply to change session state (active or disable) (ej: quit date). 

+ If the user didnt finish the session, the session is not complete and the next time they start the the module the session start over.

+ The session is recorded as complete only if the user finishes it.

+ All sessions have an unique "END" screen. (all paths end in the same screen).

+ At the end of the session the user is redirected to the app dashboard or to the first screen of the next session.

#### Possible functionalities in upgrades

+ Store the session state (in wich screen the user left the session)

+ Ask the user when start the module after quit in middle of the session if they want to start over or continue in the last screen-


Screens
-------

+ The screens can be of four types
  1. QA
  2. Number
  3. Date
  4. Slideshow

+ Each screen can be shown or not to the current user depending on the module profile.

+ QA screens can have from 1 to 4 interactions buttons.

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

+ UI components always redirect to a specific and only one screen. The only exception is the final screen of the session that redirects to the dashboard.

+ UI components can have special functions like "Module Start Over" or "Session Start Over".

+ The "END" screen have to UI componentes "GO TO DASHBOARD" and "START NEXT SESSION". 

:exclamation: **Alert**: In the current wireframe version the only screen "wrong" with the past statements are "NRT No 2" from session 2 and "Calendar" from session 1.2.


#### Possible functionalities in upgrades

+ Some user interactions can add/delete/modify fields in the module profile.




