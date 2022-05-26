---
title: "Staying with Evernote"
date: 2021-12-31 16:20
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
excerpt: Staying with Evernote 10 -- it is good enough
---
### In the (my) beginning

I have been using (and paying for) [Evernote](https://evernote.com) since [2008](/blog/2008/08/25/evernote/).  It had many innovative features: 

* good search including inside PDFs and text within images
* phone-based scanning application that produces Evernote pages, and if the scan is of a business card provides the ability to start an entry in the contacts application.
* They had an interesting storage limitation -- choosing to limit the uploaded amount per month rather than the total storage on the server.  I use *[Filterize](https://filterize.net)* to provide automation by clearing completed checklists, auto-tagging notes, generating "table of contents" type pages.

### The Storm -- Evernote 10

The move to Evernote 10 and an [Electron implementation rather than a native implementation](https://evernote.com/blog/new-windows-mac/) generated a good bit of turmoil because Evernote chose to release a product that did not have all the prior features.  Some features have come back, some have not (and probably won't).  The big problem for me was that the new approach was not optimized and was very power-hungry -- my 6-8 hour battery life turned into 1.5-2 hours with Evernote running.

### The Search for the promised land

For the last two years, I have maintained an Evernote Alternatives page tracking the features I need and information about how other apps stack up to this list of features.  Applications that have been looked at include

* [Apple Notes (part of macOS)](https://www.apple.com/macos/monterey/features/) - which continues to improve each release
* [Obsidian](https://obsidian.md)
* [Craft](https://www.craft.do)
* [Joplin](https://joplinapp.org)
* [DevonThink](https://www.devontechnologies.com)
* [Nimbus](https://nimbusweb.me)
* [Notion](https://www.notion.so/product?fredir=1)
* [Bear](https://bear.app)

The website [NoteApps.info](https://www.noteapps.info) is an excellent tool for looking at the various alternatives to look at important dimensions.

Of course, it is hard to change.  I have over 5800 notes (down from 8000).  I have used Evernote to export slices of this to their ENEX format and then [evernote2md](https://github.com/wormi4ok/evernote2md) to convert the information to Markdown to import to other apps.  Even though quite a few things have changed along the way, I am far along the learning curve with Evernote, and migrating over is challenging.

### There is no place like home (even with its problems)

I have recently upgraded to a MacBook Pro 14 with an M1 Pro chip.  Between the improved M1 Pro efficiency and the improvements that have finally occurred with Evernote, the power issue is substantially less painful and no longer driving the need to change.  Had it not been for the pandemic-driven reduction of my travel, I would have been forced to either migrate or not keep Evernote loaded.  Of course, Evernote made the second option challenging since they don't support starting up offline, forcing a traveler to keep it loaded if it is the center of their information universe.

With the power issue mitigated, I have ended my alternative evaluation and will stay with Evernote.  Today I am deleting the Joplin, Craft, and Obsidian programs and moving back to focusing on my work rather than the search for an Evernote replacement.  Undoubtedly, these products, Evernote, and others are building very innovative, useful products and seem to each have their passionate followers.  One can visit the [Evernote Forums](https://discussions.evernote.com) and see that not everyone has stopped searching for other tools.  My present conclusion is that Evernote has several problems, but so do the alternatives, and I know less about them.  It is good enough!

Recent neat things that make Evernote even better for me feature-wise include:

* <del>Grammarly Desktop works inside Evernote (done by Grammarly, not Evernote)</del> [^1]
* Google Calendar linkage to notes
* Tasks
* Home view of Evernote
* Reinstatement of the ⌘+ J search shortcut


### Suggestions for a Brighter Future

Things that I think they need to do

1. Make an M1 native (or universal) app for the Mac.
2. Let me start the desktop version without the network.  I understand there may be a reason to check in with the server, but I think that could move to only be required on a weekly or monthly basis rather than each startup.
3. Provide an efficient backup mechanism (it would also help in migrating, of course). They should look at Google Takeout.
4. Provide a way to reset checklists for re-use
5. Avoid regressions in sync that cause duplicate copies

Things that would be nice for them to do:

1. Support source code highlighting and graphics like [mermaid](https://mermaid-js.github.io/mermaid/#/).
2. Restore the Sync button to the desktop to allow one to know that all syncing that can be done has been done.


[^1]:  Evernote and Grammarly Desktop are *not* working together after just a brief time when they did.  This is acknowledged by both vendors ([Grammarly's post][GPost]) so it may be a while before this support returns. (added 20220526)

[GPost]: https://support.grammarly.com/hc/en-us/articles/4428282986893-Grammarly-for-Mac-doesn-t-work-in-certain-apps-for-Mac