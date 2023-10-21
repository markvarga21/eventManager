# CONNECT

This repository holds the software architecture of the out event manager application named **CONNECT**. Also, it provides brief descriptions about each service, their usages and functionalities and the upcoming problems with it.

---

## CRUD service (_microservice_)

- It enables authorized/logged in users to create, read, update and delete events.
- Users can have two states for an event: `Going` or `Interested` (mostly like Facebook)
- There would be two types of events:
  - **Organization events**: events made by organizations like the University of Debrecen, or the City of Debrecen etc.
  - **User events**: these are much smaller events, for example if a friend group is going out or anything else, they could arrange it using this applications built-in features, thus easing the whole management (if the friend group is large).
- Age restricted events.
  - for example there could be events specifically made only for children and some events, like action events could be restricted only to adults.
  - thus, children could not register no non-children events
- There could be a list of the performers of the event.
- Users can also rate or un-rate events.
  - up- and down votes like 9GAG
- There will be separate pages for every event, where the registered users, organizers can talk with each other.
  - Facebook event page like
- Maximum personnel capacity for an event for safety reasons.
- In some situations, performers can share the album or the titles of the playlist they've played on the event.
  - i.e Spotify, YouTube etc.

## User management service (_microservice_)

- Simple single users, or multiple can be registered for an event (i.e friend groups, couples, families etc.)
  - this also provides the possibility to register to an event
- Users can alter their data and to make CRUD operations on their personal information.

## Recommender service (_microservice_)

- The events will be tagged, for further usages, for example when determining a users specific interest.
  - at first, upon first login, there could be a form, where the user can fill in his/her interest areas and other important things, which will help to determine his/her interests
    - this can also be achieved using the **Virtual assistant microservice**
- Also, there will be a multi-class classification model, which helps to determine what interests does the person have.
- There could be a dress code for every event.
  - i.e formal, informal, business, business casual etc.

## Ticketing service (_event driven_)

- The tickets could be an NFT (Non Fungible Token) illustration related to the theme of the actual event.
- Users can represent their tickets only by holding their phone close to a machine, using NFC technology.
  - basically, it would work like a hand-band
- The transactions could be based on a blockchain implementation

## Notification service (_microservice_)

- This service would inform users about upcoming events via SMS, email, push notifications (if mobile app is used and already implemented) etc.
  - it can use already made services when sending SMS or email
- This service also provides users to send custom designed invites to their friends or to anyone.
  - lets user to send or share event invitations via Facebook, Instagram, Twitter, simple email or else

## Import-export service (_microservice_)

- **Exporting**: there could be a functionality for exporting events to the Google or Apple Calendar or to other related application.
- **Importing**: user could import already made events from other platforms like Facebook.
  - this would use the official Facebook API, or web scraping technologies

## Authentication-authorization service (_microservice_)

- The application would have an authentication service, thus allowing only registered users signing up to the events.
  - for this, users can sign up/in using their email addresses, Google-, Facebook- and Twitter accounts (or any other social account)
- The authorization parts could come handy when speaking roles like: **admin**, **organizer**, **staff**, **voluntary** and other roles.
  - at first, every user has a base role, and after an event is created by himself/herself, the **organizer** role will be assigned to him/her, who could assign more people to this or the lower roles
  - people with **admin** role could alter all the data entered in the application
- This could be achieved using already made services, for example **Firebase** Authentication and Authorization support.

## Live feed service (_event driven_)

- There could be live stories, forum, comments, videos, pictures relating to the actual event.
  - comment and image stream like on Twitter
- There will be group chats for newly forming social/friend groups.
  - group chat types: **event-type based** or **event based** chats
- There would be some QR codes on the event site, where people can take group photos or videos and then share it to the common group/event feed of the event.
  - there would be some limitations like the maximum number of uploaded pictures per user (for example 5 images) for handling unexpected data growth
    - this also ensures that the text-image ratio is balanced on the live feed of the event

## Supporting service (_microservice_)

- Lets organizers to make polls and forms about an event or a series of events.
  - this makes possible to discover user wills and needs
    - i.e preferred musics, performers, timings, drinks, foods,
  - polls can be created
- FAQ (Frequently Asked Questions) section.
  - here a LLM (Large Language Model) can be used like _llama2_
- Forum.
- The sponsors of the event.
  - for example when registering a festival

## Gamification service (_microservice_)

- Leaderboard, badges (can be achieved for completing certain tasks or challenges), giveaways, contests etc.

## Location service (_event driven_)

- This service ensures that each person in the group finds the others, if they were separated for some reason.
  - this could use a live map, or a QR code based map, where the codes would be placed on common (previously) known places
- This could use services like Google Maps API, or even location information inside a building.
- Offline availability.
