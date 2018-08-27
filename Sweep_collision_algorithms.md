I'll try to describe some algorithms for collision detection. These algorithms are sweep tests, meaning that they can test for collisions along a path.

There's an [example application](Collision_test_app "wikilink") that shows an implementation of these tests.

I just found an excelent tutorial about this collision stuff. So better go reading <http://www.harveycartel.org/metanet/tutorials/tutorialA.html> instead of my stuff :)

Rectangle-Rectangle-Sweeptest
-----------------------------

![](Rect_rect_sweep.png "Rect_rect_sweep.png")

We have 2 rectangle r1 and r2, and a movement vector v that represents the relative movement of r1 to r2. The vector v has x and y component written as v.x and v.y, the rectangles have x1, y1 as their upper left point and x2, y2 as the lower right point, written as r.x1, r.y1, r.x2, r.y2.

2 rectangles collide if and only if they overlap on all axis. The trick of this algorithm is to calculate the collision separately for each axis and then combine the results to find the real collision.

The position of a point on the (first) rectangle at a give time t can be calculated with the formula `p(t) = p + v * t`.

Or if we only look at the x-axis: `p.x(t) = p.x + v.x * t`

An intersection with the 2nd rectangle on the x axis starts to happen if p crossed the upper-left point of the 2nd rectangle. At this moment the x values of p is the same as r2.x1. We can easily calculate the time when this happens:

  
`p.x(t) = r2.x1 <=> p.x + v.x * t = r2.x1 <=> t = (r2.x1 - p.x) / v.x`

Analogue we can calculate the time when x leaves the area of the rectangle by checking for collision with r2.x2.

Now we can calculate t\_min\_x the time when a collision on the x-axis begins and t\_max\_x the time when the collision on the x-axis is over. We do the same for t\_min\_y and t\_max\_y. The 2 rectangles abviously collide when we have on overlap on both the x- and the y-axis. So if t\_max\_y is not smaller than t\_min\_x and t\_max\_x is not smaller than t\_min\_y, then the time when the 2 rectangles collide is `t = max(t_min_x, t_min_y)`.

[Category:Developer documentation](Category:Developer_documentation "wikilink")
