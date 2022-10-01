---
title: "Obsidian Evernote Notes"
date: 2022-09-30 21:00
last_modified_at: 2022-09-30 21:00
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
  - "#obsidian"
excerpt: Tradeoffs -- maybe two separate articles





### backup

Both systems internally track changes and provide some protection from human error.  With Evernote, you are trusting your data to the cloud and, until recently, backup of a large number of Evernote notes (post V10) was difficult.  Recently, an open source evernote-backup has appeared with seems to make a complete backup with little effort into a local SQLite database and then provide a way to quickly sync changes in the cloud down to the local database.  Alas, while the database seems to have everything, it 

### Sharing

(Easy) sharing requires all parties to use the same system.  It is probably fair to say that readers will find Evernote easier to pick up than Obsidian.  For my wife and I, the issues are 1) partial sharing, 2) ease of finding information, 3) printing and 4) organization.

I share some content with my wife.  I want to share the information that I think may be useful to her in a form she can use (or print it) but there is lots of information that is not of interest or useful to her that should not be in her copy.  In Evernote, we shared some Notebooks and I had to make sure to share the appropriate newly created ones and then they had to be place in the right "location" within her Evernote structure.  In Obsidian, I adopted the PARA structure (folders: 1Projects, 2Areas, 3Resources, 4Archive) and modified such that folders directly under any of the PARA folders sync to her except for the folder "\_" where I put folders that are just in my system.  Obsidian has a mechanism for each machine to exclude items and we just exclude the items under these "\_" subdirectories.

I built a custom home page for my wife which is supposed to have a table of contents of the the items that are most likely being sought.  This is an evolving page.  There is also instruction about how to do a title search when the table of contents is inadequate.  It is much easier to have a very cross-linked system in Obsidian than in Evernote.

Evernote printing is a bit better than Obidian although nether follows the macOS default approach.  A button was added to the Obsidian collection of buttons to help make printing easier.

Linking organization is smoother and IMO better in Obsidian.  Moving pages around in Obsidian works great for the basic page but sometimes the resources for the page (images) stay where they were before.  This seldom is a problem but it does tend make the behind the scenes file structure confusing.  Evernote seems to put everything together in a blob so that moving the page moves all the resources of the page since you are just moving the blob.
