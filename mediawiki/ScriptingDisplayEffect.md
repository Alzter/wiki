__NOTOC__

== Summary ==

<tt>DisplayEffect</tt> is an interface for toying with the display.

== Instances ==
SuperTux creates an instance named <tt>Effect</tt> when starting the scripting engine. Its usage is preferred – creating another instance might have unexpected side effects and is strongly discouraged. (Use <tt>sector.Effect</tt> in the console.)

== Methods ==
{| class="objectlist"
! class="method"| fade_out(float fadetime)
| Gradually fades out the screen to black for the next <tt>fadetime</tt> seconds.
|-
! class="method"| fade_in(float fadetime)
| Gradually fades in the screen from black for the next <tt>fadetime</tt> seconds.
|-
! class="method"| set_black(bool black)
| Blackens or un-blackens the screen (depending on the value of <tt>black</tt>).
|-
! class="method" style="vertical-align: top"| is_black()
| Returns: <tt>bool</tt>; has the screen been blackened by <tt>set_black</tt>?<br />Note: Calling <tt>fade_in</tt> or <tt>fade_out</tt> resets the return value to <tt>false</tt>.
|-
! class="method"|sixteen_to_nine(float fadetime)
| Sets the display ratio to 16:9, effectively adding black bars at the top and bottom of the screen. Should be used before cutscenes. Gradually fades to this state for the next <tt>fadetime</tt> seconds.
|-
! class="method"| four_to_three(float fadetime)
| Sets the display ratio to 4:3, removing the black bars added by <tt>sixteen_to_nine()</tt>. Should be used after cutscenes. Gradually fades to this state for the next <tt>fadetime</tt> seconds.
|}

== Constants ==

None

[[Template:Navbox Scripting reference]]
[[Category:Scripting Reference]]
