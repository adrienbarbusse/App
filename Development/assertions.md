ASSERTIONS
==========

**Author**: Juan Peist juan@john.cat

**Last update**: January 26 2018

Vocabulary / Index
------------------

[**APP**](#app): All the app, including all modules, the blog section, user profile, login and sign in logic, etc.

[**PROFILE**](#profile): All the user data and options.

[**BLOG**](#blog): Entries from medium.com.

[**MODULE**](#module): Course. It consists of a distributive page with active an non active sessions. The only one in the v1.0 is "STOP SMOKING".

[**SESSION**](#sessions): Chapters of the module. It consists of screens.

[**SCREEN**](#screens): The content unit. It consists of text, animations and UI. For now there are 2 types of screens: QA screens, slideshow screens.

[**TIPS**](#tips): Section. TIPS that will help the user to fulfill the objective of the module.

[**SOS**](#sos): UI that opens a chat or contact form (third party service: [intercom.com](https://www.intercom.com/)) 


App
---

+ The app can have infinite modules.


Profile
-------

+ The profile is composed of general fields (name, age, email, notifications settings, etc) and specific profile to each user/module (from now on "module profile").

+ The user can modify the general fields.

+ The user can turn off and on a module.

+ The user can not modify other module properties other than ON/OFF. These are modified depending on the user's interactions in the sessions.

+ Turn off a module preserve all the data (soft delete).


Blog
----

+ The user will see blog entries retrieved from a specific publication of [medium.com](https://medium.com/) via [RSS feed](https://help.medium.com/hc/en-us/articles/214874118-RSS-feeds)

+ The tags of the blog entries to be shown correspond to the modules profiles.

+ The user will only see 4 entries at a time (the last 4 by publication date) in the dashboard and a "view all" button

+ The "view all" button redirec to a screen with all the entries order by publication date.

+ Each entry have a "read time" info [see this for dev](https://www.npmjs.com/package/reading-time)

#### Possible functionalities in upgrades

+ Retrieve the entries from medium.com and store them in the lify database for consume via lify API.

+ Set entries as read in lify database.


Module
------

+ A module can have infinite sessions.

+ A module is accesible from the dashboard page.

+ A module can be reset from the user's profile. (hard delete).

+ When the user reset the module all the data associeted with the module is deleted.

+ Each module could have a [SOS](#sos) button/functionality


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

+ At the end of the session the user can be redirected to the app dashboard.

#### Possible functionalities in upgrades

+ Store the session state (in wich screen the user left the session)

+ Ask the user when start the module after quit in middle of the session if they want to start over or continue in the last screen.


Screens
-------

+ The screens can be of four types
  1. QA
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
  4. UI: Optional. Button/s 4 maximum, date or number fields. Default: "OK" button.

+ Each slide of the slideshow contains:
  1. Title: Required. Max characters limition.
  2. Body text: Optional. Max characters limitation.
  3. Image: Optional. Gif animado.
  4. Close button.

+ Each item on the screen can have 2 or 3 styles. ej: Title -> big, medium, small. Buttons-UI -> vertical, horizontal. etc. This styles must be predefinied.

+ UI components always redirect to a specific and only one screen.

+ UI components can have special functions like "Module Start Over" or "Session Start Over".

:exclamation: **Alert**: In the current wireframe version the only screen "wrong" with the past statements are "NRT No 2" from session 2 and "Calendar" from session 1.2.

#### Possible functionalities in upgrades

  + More UI types


Tips
----

+ Show one tip per day.

+ Have a Past tips subsection with a list of all tips readed by the user.

+ Each tip is displayed on a single screen.

+ Each tip contains:
  1. Title: Required. Max characters limition.
  2. Body text: Optional. Max characters limitation.
  3. Image: Optional. Gif animado.


Sos
---

+ Button present in each module dashboard section that gives access to a chat or contact form via [intercom](https://www.intercom.com)





