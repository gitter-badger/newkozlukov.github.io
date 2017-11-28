---
layout: post
---

Testing Ka$${^T}{e}{^X}$$.
I'm using [*this*](https://xuc.me/blog/katex-and-jekyll/) as a reference.
Had to make a few changes (cf. [*/static/katex_render.js*](/static/katex_render.js))

For some reason jekyll/kramdown won't put inline math in separate `<script>` blocks.
So I'm putting everything in `$$ ... $$` display blocks.
They aren't automagically placed on separate lines
    which allows them to be used for inline math as well.

Look, 'tis really faster than mathjax:

$$x(t) = e^{tA(t)}x_0 + \int_0^t e^{(t-s)A}f(s)\mathrm{d}s.$$

