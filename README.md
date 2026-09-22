# Halcyon

A WebGL brand site for a fictional coastal retreat, built as a case study.
Custom shaders, scroll-driven scenes, procedurally drawn imagery and no assets
at all.

Live: https://bxzex.github.io/halcyon/

## What is doing the work

**The hero** is a fragment shader running domain-warped fractal noise, tinted to
the brand palette. Two layers of warp are what make it read as moving water
rather than moving noise, and a banding term turns the smooth field into
something like caustics. It tracks the scroll position and drifts a highlight
toward the pointer. If the GPU will not compile it, the canvas falls back to a
still gradient and the page carries on.

**The room imagery is drawn, not photographed.** There is no photograph in this
repository. Each card is painted at runtime on a canvas: a graded sky, a low sun
placed by the card's seed, five layered dune ridges built from summed sines, a
few hundred blades of marram grass, and a pass of film grain over the top to tie
the set together. Four seeds, four different views of the same coast.

**Scrolling** is lerped: the page is a fixed layer translated toward the real
scroll position each frame, with a spacer giving the document its height. The
smoothing is frame rate independent, so a slow device converges in the same wall
clock time instead of falling further behind the longer it runs. That was a real
bug — with a fixed per-frame factor, a machine rendering at six frames a second
never caught up at all.

**Reveals** are IntersectionObserver driven, line by line for the display type
and once-only for the counters. **The reservation form genuinely validates** —
name, email shape and a date that has not already passed — and says plainly that
nothing was sent, because nothing was.

## Notes

One HTML file. No libraries, no images, no build step. Halcyon is invented; the
address and phone number are deliberately not real.

Built by [bxzex](https://bxzex.com).
