---
title: "Evernote Naming for Interoperability"
date: 2023-09-11
last_modified_at: 2023-09-11
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
  - "#naming"
  - "#interoperability"
excerpt: Naming considerations for Evernote to make improve Interoperability"
---

Evernote is extremely flexible in naming rules for stacks, notebooks, and tags.
However, this flexibility can lead to problems when trying to export Evernote to another system such as Obsidian.
This post outlines some naming conventions that one can use to improve interoperability.

## Stacks and Notebooks

Stacks are a collection of notebooks, and notebooks are a collection of notes. Many other systems map stacks and notebooks to folders, and notes to files.  Thus, stacks, notebooks, and files should follow the same naming rules as folders and files in the operating system and should: 

  1. not contain any of the following characters: `\/:*?"<>|`
  2. not end with a period
  3. not end with a space
  4. not start with a space
  5. not start with a period or tilde
  6. not contain any of the following reserved words: `CON`, `PRN`, `AUX`, `NUL`, `COM1`, `COM2`, `COM3`, `COM4`, `COM5`, `COM6`, `COM7`, `COM8`, `COM9`, `LPT1`, `LPT2`, `LPT3`, `LPT4`, `LPT5`, `LPT6`, `LPT7`, `LPT8`, `LPT9`

For example, I had used .Inbox for a Notebook but when it got ported to another system, the .Inbox directory was hidden from normal view. I had to rename it to +Inbox to make it visible.

I found notes are harder to manage within a restrictive naming convention, given the need for friendly, informative titles and auto-generated names from clipping activities.

## Tags

Evernote does not put many restrictions on tags either.  They can be multi-word with space separating the words, and can contain special characters.  However, many other PKM/Note systems do not allow spaces in tags, and some do not allow special characters.  Consider limiting tags to only alphanumeric characters and hyphens.

I found lots of issues with my tag usage.  Below are my original tags, and more interoperable tags.

| Original Evernote Tag | Interoperable Tag | Comment                                         |
|-----------------------|-------------------|-------------------------------------------------|
| !not Agenda           | NOT_AGENDA        | meta info: all caps, use _ between words        |
| command line          | commandLine       | use camel case for multi-word topics or hyphens |
| @FredJones            | FredJones         | Use Pascal case for proper names                |

You can wait to fix these problems as you migrate (if you do) but it may be useful to adopt naming conventions that provide interoperability to reduce the friction and time of migration later.

