---
title: "WikiLink Helper for Evernote"
date: 2023-09-11
last_modified_at: 2023-09-10
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
excerpt: Transform a Wikilink app link in Evernote
---

> A solution for MacOS using Keyboard Maestro

Like many folks, I have been exploring migrating from one PKM tool to another.  One of the nice thing about tools like Obsidian is that they support text links such as `[[Evernote - Converting text matching a note title to link in a note]]` which matches the title of this page.  It is a form of [WikiLink][].  Software that supports this markdown syntax operationally links to the named page when the content is typed.  Generally it is presented as underlined text emphasizing the link behavior.

Recently, Evernote introduced an "add note link" command which will insert an internal (app) link to an Evernote page at the present cursor position.  On the Mac, it is bound to ⌥+⌘+K by default.   After issuing the command, one then selects the note by either searching for it by (partial) title or by walking through the hierarchy of existing notes.  After selecting the desired note and confirming, an Evernote App Link for the chosen note is inserted at the present cursor position.

Evernote does not support the Wikilink syntax for creating links nor during import from sources that do.  This note describes a [Keyboard Maestro][] macro that will convert a selected WikiLink (or just text) to the Evernote page provided such a page or a very close match exists for those that run Evernote on a Mac and have Keyboard Maestro.  Perhaps one day, this will be a recognized pattern just like `[txt](https://address)` followed by a space gets you a link [txt](https://address), typing text inside double brackets `[[text]]` followed by a space will kick off the insertion action for an Evernote app link.

I have mapped the macro to ⌥+⌘+R (repair) since my first use case was to repair links brought over from other tools.  I use ⌥+⌘+W for something else so I never changed the shortcut.  The shortcut uses the clipboard but the original value is saved and restored.

The macro takes advantage of the fact that the Evernote search for note will essentially ignore the `[[` and `]]` if they exist as long as that is not in the title of some notes.

## WikiLink Helper for Evernote (Keyboard Maestro Macro)

![WikiLink Helper for Evernote](/assets/images/WikiLink-Helper-KM-macro.png)

## Limitations

1. If there are multiple notes that match, it may choose the wrong one.  If there is no match, the text is swallowed up.   Undo (twice) is your friend for these cases.

2. Evernote needs time to respond to when finding matching pages so there is a 1 second pause inserted in the sequence.  The amount of time was chosen to be generous on my machine (M1) but it could be that an older machine might need longer times.

## Installing

One should be able to import the macro by importing this [file][] into Keyboard Maestro.  <!-- The macro is also available in the [Keyboard Maestro] forum. -->

[WikiLink]: https://ia.net/writer/support/library/wikilinks
[Keyboard Maestro]: https://www.keyboardmaestro.com/main/
[file]: /assets/files/WikiLink-Helper-for-Evernote.kmmacros