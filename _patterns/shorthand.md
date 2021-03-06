---
category: shorthand
layout: default
---

From version 0.9 of Tidal, there are some nice ways of saving on
keypresses when working with numerical patterns.

For example, when specifying patterns of single numbers, such as:

~~~haskell
d1 $ sound "arpy*4" # gain "0.5"
~~~
{: .render}

you can miss off the double quotes, so this works fine:

~~~haskell
d1 $ sound "arpy*4" # gain 0.5
~~~
{: .render}

However, if you wanted more than one value in that `gain` pattern,
you'd have to put the quotes in:

~~~haskell
d1 $ sound "arpy*4" # gain "0.5 0.8"
~~~
{: .render}

You can also treat patterns of numbers as simple numbers in other
ways. For example doing algebra:

~~~haskell
d1 $ sound "arpy*4" # gain ("0.9 0.7" * 1.2)
~~~
{: .render}
~~~haskell
d1 $ sound "arpy*4" # gain (every 4 (+ 0.2) "0.6 0.7")
~~~
{: .render}
~~~haskell
d1 $ sound "arpy*4" # gain ("0.6 0.7" + (slow 3 "0.3 0.5 0.6"))
~~~
{: .render}

This is still quite new to everyone, so you will not see it used much
in the documentation yet.
