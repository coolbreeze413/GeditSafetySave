Summary
=======

This plugin will cause "gedit" to immediately(!) and automatically stash all 
unsaved documents. 


Details
=======

Once this plugin is installed and enabled (within the plugin listing, in 
"gedit"), all unsaved documents will begin to be watched. When an unsaved
document is saved by the user, its file in temporary storage will be deleted.
If all unsaved documents are saved by the user and all temporary files are
removed, the storage directory will be removed. All old temporary files will 
be periodically cleaned-up (currently, every four weeks).

Your unsaved documents will be stored under a directory named after the 
date/time that your "gedit" session was started. For example:

    ~/.local/share/gedit/unsaved/20131027-052807/Untitled Document 1


Lastly, this plugin will observe your "autosave" setting. If "autosave" is 
disabled, this plugin will not do anything. Otherwise, your unsaved documents 
will be stored at the same frequency. In other words, if your "autosave" is 
configured for two-minutes, this is the frequency at which your unsaved 
documents will be stored.  

Note that this won't work if you kill the application before the autosave interval is up since your changes, the last minute changes will be lost. This can for example happen when you opt for power-off system!

I am not sure, if we can have a gedit exit signal that can be caught by a plugin and use this to save everything.  

Realistically, gedit should be doing all this stuff by default, unfortunately it doesn't.  
(notepad++ does this and is by far superior to any other text editor out there, yes, even better than vi/emacs, so fight me)


Dependencies
============

invoke (Python package)  
`pip3 install invoke`


Getting Started
===============

1) clone the repo `git clone https://github.com/coolbreeze413/GeditSafetySave.git`
2) Run `invoke install` as the current user.
3) Open "gedit", and enable the "Safety Save" plugin.
4) Make sure your "autosave" setting is turned-on and configured for an appropriate frequency, recommend the lowest setting available (currently 1 minute)
