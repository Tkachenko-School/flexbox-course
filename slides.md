1) Flexbox layout (Flexible box) aiming to provide a more efficient way to create layout, align and adjust space between items in container, even if size is unknown or dynamic.
This is why we use term "flex".

Main idea is to give ability to alter width and height and order to it child elements.

It can fit to big part of process, relate to adjustment web pages for different devices and screens

Not: Flexbox is better to use for components, small sized layouts. While Grid system is better choice for large scale layouts.





2) basics
Flexbox is a set of CSS rules. it envolve a lot of things. Flexbox have a hierarchy in CSS rules.
Some rules related to a parent components (Flex Container) and child components(Flex Items)

Regular CSS blocks use Block + Inline directions.

Flexbox is based on their own directions.




3) Flexbox Axis
[image]

usually items go from MainStart to MainEnd

Main Axis - primary line along which flex items are laid off. can be horizontal or vertical.


MainStart, MainEnd - place where flex items are placed(inside container)


main size - depends on what main dimension is. it can be flex item width or height.


Cross-Axis. it's an axis perpendicular to the main aixs.
it direction depends on main axis directions


Cross-Start, Cross-End - Flex line, filled with items and placed into container.

cross-size - width or height of a flex item......






Properties for the parent


display: defines a flex container. it can on/off the Flexbox magic.
without this rule -> wouldn't work

code| container {display: flex or inline-flex}

flex-directions: defines how inside are appeared. Good and easy for manipulation. it'll manipulate main-axis.

row - left to right
row-reverse - right to left
column - same to row, but top to bottom
column-reverse - bottom to top






flex-wrap: define if flex item, that cannot fit to the Inline

nowrap - default section, all items should be one line

wrap - flex items will fill onto multiple lines from top to bottom

wrap-reverse - flex items, but from bottom to top







flex-flow (direction or wrap)
it's a short version of 2 style rules, it's save time and equal \ default settings equal to
flex-div row & flex-wrap nowrap








justify-content

more advanced version that we can have in default CSS rules. partially was done at Bootstrap(same logic, different realization by "hacks")

flex-start: items are packed toward the start line

flex-end: items are packed toward the end line

center: items centered along the line

space-between: items are evenly distributed in the line. first item is on the start line, last item on the end line.

space-around: items are evenly distributed in the line with the equal space on both sides.
first item will have one unit of space against to parent container but next item will have 2 units of space between the next item, because that next item has it's own spacing


space-evenly: items are distributed so that the spacing between any two items is equal.






align-items before flex module was this logic released, it can be done only by jQuery plugins. defines default behavior for how flex items are laid out along the cross-axis.

flex-start: cross-start margin edge is placed on the cross-start line

flex-end: cross-end margin edge of the items, placed on the cross-end line

center: items centered in the cross-axis

baseline: items are aligned such as their baseline

stretch: it's a default settings stretched to fill the container (still respect min-width/max-width)

align-content inside elements will fill the empty space by different logic (it's a very important rule)
applied to all elements inside. same to justify-content align individual items

flex-start - lines packed to the start of the container

flex-end: lines packed to the end of the container

center: lines packed to the center of container

space-between: lines evenly distributed, the first line is at start of container, last one - at the end

space-around - lines evenly distributed with equal space around each line
stretch - (default setting) line stretch to take up remaining space.



OK, it was instructions related to flex container.


====================

Properties for the children (flex items)

order: self-explanatory, before you can do it only with DOM manipulation via javascript or at server side.
default is 0.

flex-grow: important rule, because now you can calm about amount of container inside. Important
for different screen sizes. Same a lot of times for Frontend Developers that use it.
define ability to grow(if necessary) works as proportion. Number of this rule dictates what amount of
the available space inside the flex container the item should take up.
it all items have flex-grow = 1, all remaining space will be distributed equally to all children.
if one item has value 2 -> remaining space would take up twice(increased 2x) as others






Before you should add classes, that will handle that.
Only positive numbers.

flex-shrink: define an ability for a item to shrink if it necessary. negative numbers invalid.

flex-basis: define default size of an element before the remaining space is distributed.
can be a lenght or keyword.
~auto~ term means (looks only at width or height property)

~content~ keyword means (size based on content) but content is not 100% supported well

if set 0 - extra space not counting
if set auto - extra space will be distributed based on 'flex-grow' value

flex: short version
first section is equal to flex-grow,
second equal to flex-shrink
third equal to flex-basis

second, third is optional.
default setting is `0 auto 1;`

better to use this property. because it make code clear.





align-self: sometimes you need to override position of one or few elements instead of setting
rules for each item. used in custom cases only.

can align and override main rules.

float, clear and vertical align. wouldn't work on flex item.

auto:

flex-start:

flex-end:

center:

baseline:




Example: perfect centering with few elements inside container.
relies of margin auto rule. it absorbed all extra space.

Let's have a list of 6 items with fixed dimensions but they will be auto-sized.

All items will have evenly on horizontal Axis so when you resize browser, all will looks fine and without media queries
(Fuh) Media queries is good, but it's not perfect.
