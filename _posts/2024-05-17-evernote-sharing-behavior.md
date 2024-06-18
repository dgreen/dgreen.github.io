---
title: "Evernote Sharing Behavior and Implications for Family Sharing"
date: 2024-06-17
last_modified_at: 2024-06-17
comments: true
related: true
categories:
  - productivity
tags:
  - "#evernote"
  - ""
excerpt: "Evernote sharing behavior and implications for family sharing"
---

While the popups are confusing, the owner of the shared Notebook controls the behavior of the Notes, effectively owning the Notes. Having a concept of ownership is useful in some situations.  However, it presents challenges to the survivability of the Notes if the owner account is closed due to death or some other reason.

This article is focused on ownership and allowing a user to preserve content when one of the accounts is gone. It does not explore limiting access by "Edit" or "View" rather than "Share, Edit" interacts between owner settings and Notebook share settings.

Similarly, this article does not discuss trying to ensure that Notes disappear when the Note (or containing Notebook owner) account is closed.

This article discusses what happens to individual Notes in various scenarios and then lays out strategies for mitigating issues.

## Actions

### Sharing the Notebook

For this article, I created a new Notebook, SharedByDave, and then shared that Notebook with my wife through the right-click menu on this new Notebook or the `…` menu on the Notebook contents column. After I share, an email gets sent to her. She goes into Evernote, and at the bottom of the left panel, she can select `Shared With Me` and then see the new shared Notebook in the middle column. Clicking on this Notebook will cause it to be placed into her Notebook list.

After sharing and waiting for synchronization delays, the sharing status can be seen in a popup by revisiting the share steps or right-clicking on the green people in the middle pane.

![](/assets/images/CleanShot%202024-06-11%20at%2023.23.49@2x.png)

The shared Notebook is not required to be in the same stack (or be in a stack) for each user. The graphic is my view, but my wife's view of the shared Notebook is similar.

### Creating a Note in the shared Notebook

If I create a Note in the shared Notebook, it will be owned by me but visible to my wife. Looking at the Note's sharing information, I see the green people with a count of 2, showing that the Note is shared with two users. However, looking at the promised permission details, the pop-up does not show who can access the Note but does allow me to share the Note with others. This is because the effective sharing is at the Notebook level, not the Note level.

![](/assets/images/CleanShot%202024-06-12%20at%2000.04.26@2x.png) My View of Shared Note

My wife's view is more detailed. It shows that I own the Note and that she has specific permissions. While her access is shown in a dropdown, she cannot change it.

![](/assets/images/Image%206-12-24%20at%2012.09 AM.png)  My wife's view of the Note's sharing status

If my wife creates a Note in this shared Notebook I own, the views are reversed.

### Moving a private Note into the shared Notebook

If my wife creates a Note in a private Notebook, the Note is not shared. Moving the Note into a Notebook I own, I now have access just as if she had initially created the Note in the shared Notebook, but she appears to retain ownership. Our view of sharing also looks like she had created the Note in the shared Notebook.

### Duplicating a Note not owned by the shared Notebook Owner

I can take ownership of the "content" of the Note by duplicating the Note she owns (and potentially deleting the original.) The permissions will look as if I created the Note. However, if one examines the Note Info (in the Note's `…`menu), she will be shown as the author. Note that links to the original Note will not point to the duplicate even if the original is deleted.

### Deleting the shared Note in a shared Notebook

If I delete a Note in a shared Notebook I own, it disappears from both of our Notebooks but only shows in the Trash on my computer (and thus could only be restored by me) regardless …the creator/owner. If my wife deletes a note in a shared Notebook I own, it disappears from both our copies of the Notebook regardless of the creator/owner. It only shows in the Trash on my computer and can only be restored by me.

### Deleting the shared Notebook

Something unexpected happened when I, as the owner, deleted the shared Notebook. As expected, the Notebook disappeared from my computer, and the Notes were in the Trash.  The Notebook was gone on my wife's computer, but the Notes were also unexpectedly in the Trash on her computer!  This was not repeatable. In subsequent attempts, the Notes on my wife's computer were not in Trash but gone (as documented by Evernote).  Restoring the Note from Trash on placed that Note in the default Notebook.  

### Finding non-owned Notes

It does not appear that searching for non-owned Notes or Notebooks is possible other than manually examining them one at a time and looking for the non-owner pattern in the Note's share permissions.

### Tags

As Notebook owner, I can apply Tags to any and all Notes in the Notebook. My wife can only apply Tags already used within that shared Notebook. Similarly, should she take a private Note with a tag unique to her system, it will be removed when she transfers the note to a Notebook shared by me.

### Taking ownership through duplication

One can become the content owner by duplicating the Note, deleting the original Note, changing the name back to the original name (remove "- Copy 1"), and repairing any Notes that pointed to the original Note and now need to point to this Note. This does not seem to be a necessary step since the actual Note ownership information seems to be ignored when in a shared Notebook.

### Ownership is not presently part of an ENEX file

Since ownership is NOT stored in an ENEX file, one can assume ownership of the content by exporting/importing an ENEX file. There are issues with what is lost in this movement discussed elsewhere.

## Mitigation Strategies

In this section, I will explore steps to avoid losing shared content if the owner of the shared Notebook account dies.

### Chose to keep both accounts

The easiest mitigation approach is to keep both accounts. This may involve cost and, ideally, access to all credentials. This will preserve everything including links as no changes are made.  

Letting the shared Notebook-owning account lapse from paid to free (as long as those accounts are not closed) should also work. However, there is a risk that Evernote will change the rules on free accounts, which could defeat this non-paying for dormant accounts approach. I have not explored this path.

### Have one user own all Notebooks and plan to take over this account

If I own all of the Notebooks, then I am the effective owner of all content, and all content must be stored in my Notebooks owned by my account. If not all my Notebooks are shared, my wife's computer could have a subset of the data. Easy transferring ownership of the data would involve my wife taking over my Evernote account and deleting any Notebooks she does not want. She could close her account. It is possible to change the user information on an account. However, she might need a second email or userid to avoid conflicting with her original account before it is closed.

This approach will preserve the links to Notes.

### Export to ENEX and reimport (links break)

One can take ownership of the content by

- exporting a Notebook's content to ENEX,
- importing in the ENEX into a new Notebook,
- deleting the old Notebook on the original shared Notebook owner's computer, and then
- resharing by the new owner.

If one periodically backs up Evernote to ENEX files, this can be accomplished after the original shared Notebook's owner's account is terminated.

Alas, this will break all links to Notes.

A more manual version of this approach is to duplicate the files on the non-owner machine and then copy those duplicates into new private folders. It is much more work, and it may preserve some information that does not get exported into the ENEX files, but Note links will still be broken.

### Seek Evernote Enhancements

- Allow taking ownership of Notebook(s) rather than deleting (or making it an option to do so), perhaps with permission from the original account.
- Solve the ENEX linkage issue to allow ENEX recovery

## Conclusions

Understanding what will happen if one of the accounts is removed is important in planning the shared system that survives. In a non-Teams Evernote shared system, understanding who owns the shared Notebook is crucial to ensuring its Notes remain available. Evernote's current practice of moving a paid account into free status can mitigate some issues for users who still need access.

Evernote could provide additional clarity by showing the full permissions on a Note in all cases and commenting to show when the shared Notebook's permissions are used. Hopefully, they will do this and provide a "take ownership" solution for this scenario.
