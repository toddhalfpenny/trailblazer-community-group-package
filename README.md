# trailblazer-community-group-package

Salesforce app for managing Trailblazer Community Groups.

First up, let's be clear, this is a work-in-progress project.

I'm also going to be using it to hopefully be the basis of blog articles/talks on how an app on Salesforce can be built. A case-study if you will. I'll be trying to use this README (or potentially other pages) to [document the journey](#Journal) also.


## Requirements
1. 2GP Support
1. OSS
1. CI/CD
1. **No** real data to be stored in git repo
1. Backup/restore support

## Features

### MVP

Initial MVP features will be those included in the first packaged (unlocked or managed, I'm usure which yet). These features will generally be the ones that I personally believe will (mostly) meet with parity of the current non-SF tools I use in organising our TCG (Trailblazer Community Group)

1. Track planning and execution of events
    1. Presentations
    1. Speakers
    1. Sponsorss
    1. Recording links
1. Store (potential) sponsors details
1.Track prizes

### Roadmap & Other ideas

1. Event listing and stage (kanban)
1. Calendar View
    1. Show entries/clashes from google calendars / Trailblazer Community / Salesforce events
1. Sponsor Management
    1. Last time sponsored
    1. Notes on venue
    1. Contacts
    1. Sponsored amounts / prizes
    1. Opps
1. Talks
    1. Potential
    1. Tags / Topics
    1. Last time a topic was spoken about
1. Task mangement (e.g publish event, confirm speakers, etc)
1. Dashboard
    1. Members
        1. Bevy
        1. YouTube
        1. TCG
        1. Chatter
        1. Twitter
    1. Next event(s) status
1. [Quiz](https://github.com/pozil/quiz-host-app) Integration
1. Backup / Restore
1. Speakers
    1. Basic details etc
1. Track prizes
    1. Cert vouchers etc
1. Knowledge
1. Email to case?
1. Bevy Integration
    1. Crawl?
    1. Event
        1. Import / Read
    1. Check-ins
1. Mobile App
    1. Check-ins
    1. For organisers
    1. For Community
1. Slack integration
1. Quip Integration
1. Support for Community Conferences as well
1. Git Actions
    1. Create/Version diagrams when version released


## Architecture

### ERD
![ERD](/docs/diagrams/erd.png)

 - The _IFK__c_ field above is used as an external ID - used by the data impoty/export plugin I've written

### Settings
- Success Group Link
- Bevy Link
- YouTube Link
- Twitter Handle
- Twitter hashtag
- Calendar Feeds - for list calendar feeds (e.g. google calendar) to display in the calendar

## Assumptions

1. Not concerned with custom object limits
1. App will be run in a pretty much standard _Developer_ edition org.

## Development

To work on this project in a scratch org:

1. [Set up CumulusCI](https://cumulusci.readthedocs.io/en/latest/tutorial.html)
1. Clone this project and move to its directory.
2. Run `cci flow run dev_org --org dev` to deploy this project.
3. Run `cci org browser dev` to open the org in your browser.


### Diagrams

This project uses [PlantUML](https://plantuml.com/object-diagram) for it's diagram generation from src.
In VS Code I have been using [this extension](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) with the following workspace settings
```
{
    "plantuml.diagramsRoot": "docs/diagrams/src/",
    "plantuml.exportOutDir": "docs/diagrams/",
    "plantuml.exportSubFolder": false
}
```

## Journal

### Open Questions

1. Which devhub should/can be used for a project like this?


### 17th May 2020
 - Formulated initial ERD - note the one above is the latest erd - and although all the diagrams are written using plant UML - and therefore version controlled - I've decided to keep a copy of minor iteration of ERD in github to enable easier visibility.

### 14th May 2020
 - Initial project creation
 - Decided to use [Cumulus CI](https://cumulusci.readthedocs.io/en/latest/tutorial.html) following chats with their community and research. Some thoughts on this;
   - CCI supports SFDX priniciples
   - 2GP (required for this project) although not supported (at the time of writing) by CCI, you can package up 2GP projects manually using the standard SFDX CLI commands,