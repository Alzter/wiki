__NOTOC__

== Summary ==
This module contains methods controlling the player. (No, SuperTux doesn't use mind control. Player refers to the type of the player object.)

== Instances ==
Due to SuperTux's single-player nature, there is only one instance of the <tt>Player</tt> object. You can access it via <tt>Tux</tt> from a script and <tt>sector.Tux</tt> from the console.

== Methods ==
{| class="objectlist"
! class="method"| add_bonus(string bonusname)
| Gives Tux the specified bonus. Replace <tt>bonusname</tt> with either of <tt>"grow"</tt>, <tt>"fireflower"</tt> or <tt>"iceflower"</tt>.
|-
! class="method" style="vertical-align: top"| add_coins(int number)
| Gives Tux <tt>number</tt> coins.<br />Tip: Tux has to pay 25 coins to be revived at the last firefly he visited. If he doesn't have enough coins, the player has to play the whole level again.
|-
! class="method" style="vertical-align: top"| make_invincible()
| Makes the player invincible for either a predefined amount of time.<br />See also: <tt>TUX_INVINCIBLE_TIME</tt> in src/object/player.hpp for the amount of seconds that the player becomes invincible.
|-
! class="method" style="vertical-align: top"| deactivate()
| Stops the player and blocks the movement controls.<br />Tip: Don't call this in front of a horde of badguys. Carried items like trampolines won't be dropped.
|-
! class="method"| activate()
| Reactivates the player's movement controls.
|-
! class="method"| walk(float speed)
| Make Tux walk
|-
! class="method"| set_visible(bool visible)
| Shows or hides Tux according to the value of <tt>visible</tt>. Note: Tux doesn't interact with objects or badguys while invisible.
|-
! class="method"| get_visible()
| Returns: <tt>bool</tt>; is Tux visible?
|-
! class="method"| kill(bool completely)
| Hurts a player, if completely=true then the player will be killed even if he had grow or fireflower bonus.
|-
! class="method" style="vertical-align: top"| set_ghost_mode(bool enable)
| Switches ghost mode on/off.<br />Lets Tux float around and through solid objects.
|-
! class="method"| get_ghost_mode()
| Returns whether ghost mode is currently enabled
|-
! class="method"| do_cheer()
| Makes Tux cheer, if possible.
|-
! class="method"| do_duck()
| Makes Tux duck, if possible.
|-
! class="method"| do_standup()
| Makes Tux stand up, if possible.
|-
! class="method"| do_backflip()
| Makes Tux backflip, if possible.
|-
! class="method"| do_jump()
| Makes Tux jump, if possible.
|-
! class="method"| trigger_sequence(string sequence_name)
| Orders the current GameSession to start a sequence. One of "stoptux", "endsequence", or "fireworks".
|-
! class="method"| use_scripting_controller(bool use_or_release)
| Uses a scriptable controller for all user input (or restores controls)
|-
! class="method"| do_scripting_controller(string control, bool pressed)
| Instructs the scriptable controller to press or release a button. control can be "left", "right", "up", "down", "jump", "action", "pause-menu", "menu-select", "console", "peek-left", or "peek-right".
|}

== Constants ==

None

[[Template:Navbox Scripting reference]]
[[Category:Scripting Reference]]
