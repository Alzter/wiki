__NOTOC__

== Summary ==
This class provides the ability to create, edit, and remove images floating in midair on the screen, such as the SuperTux logo. It is implemented as a wrapper around a sprite, so any sprite actions are applicable.


== Instances ==
Floating Images are created in a script or from the console.
Constructor:
<code>
 <tt>&lt;floatimage&gt; &lt;- FloatingImage(string filename)</tt>
</code>
Creates a FloatingImage from <tt>filename</tt> (which is relative to the data root).
=== Example ===

Definition of the logo in the menu level:
<code>
 (init-script "
   logo <- FloatingImage(\"images/objects/logo/logo.sprite\");
   logo.set_anchor_point(ANCHOR_TOP);
   logo.set_pos(0, 30);
   logo.set_visible(true);
   // Suspend (this is needed so that logo doesn't get deleted)
   suspend();
 ")
</code>

The above creates a floating image name "logo", anchors it to the top, set its position relative to that anchor, and finally displays it instantaneously. To use this in the console, remove the init script and ending lisp tags.

== Methods ==
{| class="objectlist"
! class="method"| void set_layer(int layer)
| Moves this image to the layer <tt>layer</tt>. See src/video/drawing_context.hpp for the predefined layers and their values (note that you can't yet use these constants in your Squirrel code).
|-
! class="method"| int get_layer()
| Returns: <tt>int</tt>; the layer the floating image is on.
|-
! class="method"| void set_pos(float x, float  y)
| Sets the position of this image to (x,y) | Move the image in relation to the current anchor point.
|-
! class="method"| int get_x()
| Returns the x position of this image. | Get the image's X coordinate relative to the current anchor point.
|-
! class="method"| int get_y()
| Returns the y position of this image. | Get the image's Y coordinate relative to the current anchor point.
|-
! class="method"| int get_anchor_point()
| Returns the current anchor point of this image. (See set_anchor_point for a list of values) | Returns: <tt>int</tt>; the current anchor point
|-
! class="method"| void set_anchor_point(int anchor)
| Set the image's anchor point. Possible values are represented by the [[ScriptingGlobals#Constants|ANCHOR_* constants]].
|-
! class="method"| string get_action()
| Returns the name of the current action of this image. (Only useful for sprites)
|-
! class="method"| set_action(string action)
| Sets the current action of this image. (Only useful for sprites)
|-
! class="method"| bool get_visible()
| Returns the current visibility of this image.
|-
! class="method"| set_visible(bool visible)
| Shows or hides the image abruptly according to visible (drastic counterpart to <tt>fade_in</tt> and <tt>fade_out</tt>).
|-
! class="method"| fade_in(float time)
| Fades in this image for the next <tt>time</tt> seconds.
|-
! class="method"| fade_out(float time)
| Just the opposite of <tt>fade_in</tt>.
|}

== Constants ==

None

[[Template:Navbox Scripting reference]]
[[Category:Scripting Reference]]
