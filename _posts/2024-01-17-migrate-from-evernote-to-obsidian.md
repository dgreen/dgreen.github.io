---
title: "Migration from Evernote to Obsidian"
date: 2024-01-17
last_modified_at: 2024-01-17
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
  - "#obsidian"
excerpt: "An approach to migrating from Evernote to Obsidian"
---

This article discusses migrating content from Evernote to Obsidian.   ~While I have decided to stay with Evernote presently, I have worked through the migration and tried out Obsidian several times.  It is my current "plan b" should something come that makes Evernote cease to make sense for me.  I decided I should collect my notes so I could save (and share) what I have learned about migrating from Evernote to Obsidian.  My latest cycle was with Evernote 10.92.3 to Obsidian 1.6.3.

## Why Obsidian
Some of the features that might encourage one to migrate to Obsidian:
- Powerful
- Has a mechanism for family sharing that I have worked out which allows limited files to Bev and all files to me with linkage (as does Evernote)
- Local Files
- Markdown
- Grammarly works
- Better linkage
- Bug level seems low with fast potential reconciliation
- Some graphics creation
- Shared content won't disappear with disappearance of account owner
- Software development not routinely exposing (paying) users to regression bugs
- URIs work
- Price

## Why Obsidian hurts
No tool is an exact match for Evernote, so there are places where Obsidian may be considered undesirable (or for some even unacceptable):
- Collaboration on a subset of the collection (vault) is difficult
- One may not feel comfortable editing Markdown
- Reorganization can be a bit challenging with attachments
- Table limitations
- Auto OCR is limited
- Multi-component updates (styles, plug-ins, core, installer)
- Mobile client can be challenging, UI and subject to overload with my vault sizze

Notes in Evernote appear to contain text, links, and various attachments.  When you move a note, everything moves.  When a note links to another note, the linkage is done by an identity string that is independent of the Note title, the Note's present Notebook, and the Notebook's Stack.  So moving Notes around does not break links nor raise any issues with embedded content.   In Obsidian, the basic note file is a markdown text file.  It contains links to files that are embedded in the note (from the user's point of view), and linkages are based on filenames.  Alas, Evernote does not presently help too much with linkages to other notes.  The exported ENEX file notes a link to another Note, but the linkage is based on the displayed text (not the underlying identity code).  This means that if the link in the Note in Evernote has a text view that matches the title of the destination Note, then the migration process will create a successful linkage, but if the original text view does not match the title, then a broken link will result.  This happens if the text view has been manually edited or if the destination Note's title has been changed without going back and fixing the text view of the link.   There is more flexibility in linking in Obsidian that can be exploited post-migration.

### Text vs Title Note Link Representation in Evernote

Evernote has three represenations for note links: 1) text, 2) title and 3) preview.  The linkage that Yarle does is by text. If the format is title, then the text will be the (original) title.  One can "fix" text links if there has been a text change or a title change by toggling the link from text to title format and back.  Alas, I don't know of automated way to do this across all notes.

## Migration Approaches
One can either migrate everything in Evernote to Obsidian, start anew in Obsidian, or do a partial content migration.  In any case, the Evernote account may be used as an archive (for free, at least under the present Evernote policy).
## Migration (assuming there is data to move)
Basically, the steps are:
1. Pre-migration clean-up
2. Export to ENEX Files
3. Conversion of ENEX files to folders
4. Installing folders in Obsidian

### Pre-migration clean-up
Since Evernote and Obsidian have different rules for tags and titles, you may wish to do some pre-work in Evernote before beginning the process.  I have written an [article](https://glimmer.gwizlabs.net/blog/2023/09/11/evernote-naming-for-interoperability/) discussing some of the issues.


The [Yarle documentation](https://github.com/akosbalasko/yarle#note-links-over-notebooks-no-problem-here-is-what-to-do) suggests making a TOC note of all notes in each notebook to reduce errors in bad linking due to duplicate note names.

### Export to ENEX Files

After any note cleanup, the Evernote content may be exported to ENEX files.  It is probably best to do this Notebook by Notebook, either using a desktop Evernote client or all notebooks at once using a tool like [evernote-backup](https://github.com/vzhd1701/evernote-backup). 

A limitation of evernote-backup is that it does not handle the new Evernote Task since the Evernote API it uses does not support Evernote Tasks.  A workaround is to use the desktop client to export those specific notebooks to override the ones made by the evernote-backup export` process.

### Conversion of ENEX files to folders
There are two approaches to the conversion of ENEX files to folders. They both transform ENEX files into folders with the same name as the ENEX file.  There is a community plugin named [Importer](https://help.obsidian.md/Plugins/Importer) that can do the import process with certain decisions built in to the process.  The Obsidian help site has [details on its usage](https://help.obsidian.md/import/evernote).

#### Obsidian Importer
This community plug-in needs to be installed, and then it is simply a matter of pointing it at your ENEX files and doing the import.  The imported Notebook (folder) may need to be moved into the correct location in the folder in your structure.

The built-in decisions of the Importer cause
1. Duplicates the filename as an initial H1 (heading) in the file
2. Does not on, its own, put things into folders associated with stacks
3. Insert hex codes A0 20 at the end of line from time to time
4. Does not handle BusyCal event URIs as well as many others
5. Does not handle tel URIs
6. Does not translate Evernote Note tasks to Task Plug-In tasks but rather to just a checklist item
7. Converts tags like IGNORE_OT converted to IGNORE/OT
8. Puts attachments in a lower-level folder per page (which is probably a good compromise), but it does not seem to be supported by the basic Obsidian approach. There is no "in a subfolder named for the note, which is itself in a subfolder under the current folder". 

#### Yarle Importer
The second process is to use the standalone tool Yarle to maintain more control of the process.  This is more flexible and allows one to use the current version of Yarle.

![Welcome | Select Enex files | Configuration | Set Template | Pick an output location | Convert](/assets/images/image-20240112233718590.png)
Top panel in the Yarle tool.

As shown above, there are several input steps followed by conversion:
1. Welcome - documentation on Yarle and the conversion process
2. Select Enex files - select all the ENEX files you want to import with this pass of running Yarle
3. Configuration - control the conversion (see below)
4. Set template - control the structure of the generated note
5. Pick an output location - I tend to pick a space that is NOT inside an Obsidian vault
6. Convert - let Yarle do its thing

I have decided to migrate all ENEX files at once, so I select them in blocks and just let them accumulate in the tool.  You can move to different folders and select them.  Note that they will all be placed into a set of folders at one level (losing which Notebook was in which Stack).  I use a simple script to restore the Stack (nested folders) structure that I want in Obsidian but this could be done manually.

In the **Configuration** step, I use the following (where red boxes highlight changes from the default):

![The options used for Yarle](/assets/images/yarle-options.png)

In the **Set Template** step, I replace the default template with the following:

```yarle
---
{tags-array-block}tags: {tags-array}{end-tags-array-block}
{location-block}location: {location}{end-location-block}
{reminder-time-block}Remind: {reminder-time}{end-reminder-time-block}
{source-url-block}url: {source-url}{end-source-url-block}
{created-at-block}created: {created-at}{end-created-at-block}

{content-block}{content}{end-content-block}
---
```

#### Convert
This step may take a while, and the status display quickly fills up and becomes hard to scroll with a large number of ENEX files.   I tend to look at the output directory to see an ever-increasing number of files and folders to check progress. 

### Installing folders into Obsidian
I arranged the folders representing the imported Notebooks into the structure I desired (very similar to the Stack structure in Evernote) and then moved the collection into the Obsidian Vault (folder).

At this point, Obsidian should recognize the files and reindex.  It will do this automatically when starting if needed.  

You can now look at the new files and begin to look around.

I recommend Custom Attachment Location plugin which will try to keep the structure of attachments "sane" where a note yyy in the folder xxx will have it's attachments in xxx/_resources/yyy.  

## In closing

As noted in the beginning, the migration to Obsidian has not stuck (yet).  I have written this up to share with others and to record the process so that I can relatively quickly do the migration again if needed.  My Evernote account has about 9000 notes and the exported ENEX files occupy about 5GB.  Using an already sync'ed `evernote_backup` database, I can export the ENEX files, run Yarle and get them into Obsidian in 4 hours or so.  If I manually export ENEX for each Notebook containing a reminder or an Evernote Task, it can take a bit longer.

There will be broken links due to a variety of issues, the most frequent being the renaming of a note without going back to the source note and changing its link text.  I find that I can usually figure out the correct linkage but if not, I can go to Evernote and figure things out and manually fix them.  All in all, the migration from Evernote to Obsidian with this approach works pretty well and requires fewer fixups than all the other tools I have tried migrating to.

---

### 2024-06-20 Update
1. Updated the section on the Yarle Importer to reflect the configuration used.
2. Updated the Obsidian Pros and Cons to reflect my current thinking and changes in Obsidian and Evernote.


### 2024-01-27 Update
1. Added suggestion from Yarle documentation re TOC note
2. Added section on Evernote Note Link Representation