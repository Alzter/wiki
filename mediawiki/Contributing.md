So you would like to '''contribute''' to ''SuperTux''? Great! We can use all the help we can get. The following instructions should get you started.

== Why ==
*Show your changes to the world, and contribute them to the project!
*You get write access to our repository and join the team if you contribute enough.

== Test new levels ==

The easiest way to contribute to ''SuperTux'' is actually fun: Play the new "for testing" levels and tell us what you think. Just go to
:''Main menu'' → ''Contrib Levels'' → ''[[Incubator Island]]''
and play the levels you find there. Then log on to [[IRC]], a chat network, and tell us what you think. Or send an email to the [[mailing list]]. Or see if there is a "bug report" in our [[bug tracker]] that handles the new level.

We're especially interested to hear about the following points:
* Where did you die the most? Did you die at all?
* Can you collect all the coins in the level?
* Did you find all the secrets?
* Did any [[badguy]]s die / fall down before you reached them?

== Licenses ==

We can't use contributions that aren't redistributable under the same license as SuperTux itself.
Usually, GPL will infect small code changes automatically. For everything else (like levels, images, sounds, and new programs), make sure that you can release it under GPLv2 or later (yes, ''all'' contributions need to be released under GPL) and also CC-BY-SA for data files such as images, sounds, music, and levels. (Scripts count as parts of levels)

== Generic instructions ==
These instructions apply to every function you may want to adopt.
#Join the SuperTux [[Contact#Mailing List|mailing list]] to stay up to date with recent developments.
#Check out the latest SuperTux [[Download/Subversion|development version]] and compile it by following the instructions in the [http://supertux.lethargik.org/svn/supertux/trunk/supertux/INSTALL INSTALL file] if you want to develop code or levels.
#Modify or add something that is either listed in the [[Milestone 2 Design Document/Tasks|task list]] or seems useful to you.
#Give us your work:
#*The preferred way is to open a new report on our [{{MediaWiki:bugtracker-url}} bug tracker] and attach the files to it. (You can upload and attach files to bug reports using the “Upload File” button when filing or perusing them).
#*Alternatively, upload the files to some website or ftp server and send us the link on the mailing list.
#*Do NOT use attachments on the mailing list; the files tend to get big, annoy people, and the mailing list often eats them

== Data Files ==
Contributions which mostly add new files (typically when creating new graphics, sound, music, levels) can simply be put into an archive (preferably .tar.gz or .zip).

The developers will review your work and, if everything seems in order, check it into the repository.

=== Translators ===

Please see [[Translation]] for instructions.

=== Artists ===

Please use the PNG format for small graphics and the JPEG format for large ones.
It would be helpful to keep and send the source files as well (the GIMP's .xcf is preferred) so that the team can reuse the image.

Hints:
* [http://pingus.seul.org/~grumbel/tmp/tilehowto.png Little Guide for drawing tiles that tile properly]
* [http://pingus.seul.org/~grumbel/gimp/drawing/ Little Guide on how to get the graphic style that is used in the game]

=== Level designers ===

Your level should try to follow with the [[Milestone 2 Design Document/Styleguide|level guidelines]] set by the ''SuperTux'' [[team]]. See the [[Editor FAQ]] for some help on using the Supertux-sharp editor.
If your levels break the rules or you don't want them as part of the main world, try [[CreatingMods|packaging them as an addon]]. (Note that addons can be under licenses other than GPLv2 and CC-by-SA, though they should allow non-commercial distribution if you want them be in the addon manager)

Once you have created a cool and awesome level, open a bug report in the [[bug tracker]] and attach your <code>.stl</code> file. If the level looks like a candidate for the main game, it may be included in the [[Incubator Island]]. Please don't feel bad if you are asked to do a couple of changes on your level prior to it being accepted as a candidate; in order for ''SuperTux'' to be a fun game, there must be some consistency between all levels in the game.

== Programmers/Code ==

Changes to the code typically affect only parts of bigger files, so it's hard to spot the differences to the original file. Therefore, we ''strongly'' recommend sending code contributions in the form of a patch. (Patches also happen to be smaller than full files) This guide will walk you through the process of creating a patch.

We assume that you have a current checkout of the SuperTux repository (see [[Download/Subversion]]) with your changes applied. Then you should first use
<code>
 svn update
</code>
to merge in other developer's changes.
<code>
 svn status
</code>
will print a list of files with a prefix letter. M means you changed the file, C means there is a conflict between your changes and changes from someone else, ! means the file is missing, and ? means the file is ignored by the version control.

You should fix conflicts by editing the conflicted file and then using '''svn resolved <filename>''', add files to version control with '''svn add <filenames>''', and remove existing versioned files with '''svn remove'''. (Note that files are never really deleted; you may always check out a former revision when the file still existed.) Finally you can create a patch using Subversion:
<code>
 svn diff *files* > mypatch.patch
</code>
This will create a file mypatch.patch that contains all changes in the listed files. (You should open the file in a text editor and verify that it contains all your changes but only changes you want to submit). Omit the files argument completely to include all files that have been changed.

Now you can send off ''mypatch.patch'' using the generic instructions. If you want to apply a patch generated using ''svn diff'', use the following command:
<code>
 patch -p0 < apatch.patch
</code>

== Improving the wiki ==

You can easily help ''SuperTux'' by updating the wiki. This can be done without any programming skills whatsoever. We use ''categories'' to organize pages that need attention. This way it's easy for you to find someplace to start working. Some of those categories are listed below. All maintenance categories are included in the [[:Category:Wiki Maintenance]].

* Pages in [[:Category:Outdated]] include outdated information that may not reflect the current state of the SVN repository. You can research the current state and adapt or replace the outdated information.
* [[:Category:Badguys with unknown burnability]]: Badguys where the ''"Burnable"'' attribute is unknown or incorrect.
* [[:Category:Badguys with unknown buttjumpability]]: Badguys where the ''"Buttjump"'' attribute is unknown or incorrect.
* [[:Category:Badguys with unknown freezability]]: Badguys where the ''"Freeze"'' attribute is unknown or incorrect.
* [[:Category:Badguys with unknown squishability]]: Badguys where the ''"Squish"'' attribute is unknown or incorrect.

If you're unsure if the observed behavior is incorrect (and the differing documented behavior is the intended way), please don't hesitate to ask a developer or open a [[Bugs|bug report]].

[[Category:Development]]
[[Category:Meta]]
[[Category:Outdated]]
