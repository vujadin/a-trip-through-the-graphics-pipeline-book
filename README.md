# A Trip Through the Graphics Pipeline 2011

> The following is a clone of Fabian Giesen's amazing series on the graphics pipeline, cloned under his public domain license. Grab a ePub or PDF version of it and enjoy the read. 

This a series of blog posts I've written about the D3D/OpenGL graphics pipelines as actually implemented by GPUs. A lot of this is well known among graphics programmers, and there's tons of papers on various bits and pieces of it, but one bit I've been annoyed with is that while there's both broad overviews and very detailed information on individual components, there's not much in between, and what little there is is mostly out of date.

This series is intended for graphics programmers that know a modern 3D API (at least OpenGL 2.0+ or D3D9+) well and want to know how it all looks under the hood. It's not a description of the graphics pipeline for novices; if you haven't used a 3D API, most if not all of this will be completely useless to you. 

I'm also assuming a working understanding of contemporary hardware design - you should at the very least know what registers, FIFOs, caches and pipelines are, and understand how they work. Finally, you need a working understanding of at least basic parallel programming mechanisms. A GPU is a massively parallel computer, there's no way around it.

Some readers have commented that this is a really low-level description of the graphics pipeline and GPUs; well, it all depends on where you’re standing. GPU architects would call this a high-level description of a GPU. Not quite as high-level as the multicolored flowcharts you tend to see on hardware review sites whenever a new GPU generation arrives; but, to be honest, that kind of reporting tends to have a very low information density, even when it's done well. Ultimately, it's not meant to explain how anything actually works – it's just technology porn that's trying to show off shiny new gizmos. Well, I try to be a bit more substantial here, which unfortunately means less colors and less benchmark results, but instead lots and lots of text, a few mono-colored diagrams and even some (shudder) equations. 
