# Documentation

The major documentation technical barriers to be overcome in the Kepler
project are:  
   
 -- For the distribution, a consolidated web site section of all
documentation for all modules in (X)HTML format, hopefully laced
together by an index page.  
   
 -- Making that section separately searchable (can't rely on web search
engines for pages that will be continuously updated).  
   
 -- Replicating that section as a module for LuaDist so that users can
review documentation before installing modules. *Query,* whether the
search capability can be incorporated in this module? Framed HTML
formats such as WebBook are problematic for search indexing purposes
because framed pages have no URLs.   
   
 -- Setting some minimum documentation requirements for modules,
introduced gradually and hopefully followed by others as advantages
become apparent.  
   
 See related page on the wiki at
[http://lua-users.org/wiki/DocumentingLuaCode](http://lua-users.org/wiki/DocumentingLuaCode),
particularly its *Integrating Module Documentation for Distributions*
section with insightful thoughts by David M. and Hisham.   
   
 [LuaStyleGuide](http://lua-users.org/wiki/LuaStyleGuide) - has a few
notes on commenting.  
   
 Known existing code documentation tools are listed below (there are
likely more).  
   

## DecoratorsAndDocstrings

[Annotate module](http://siffiejoe.github.io/lua-annotate/) Annotations and Docstrings for Lua Values.

[DecoratorsAndDocstrings](http://lua-users.org/wiki/DecoratorsAndDocstrings) has
methods for associating documentation with objects at runtime.  
   
## ExpLua

[ExpLua](http://lua-users.org/wiki/ExpLua) is both a code comment format
and a tool for extracting said comments and exporting HTML, LaTeX, and


whatnot. It is freely available for use under the same License as the
Lua project, with the usual disclaimers.  
   

## LDoc

[https://github.com/stevedonovan/LDoc](https://github.com/stevedonovan/LDoc)  
   
 Successor to [LuaDoc](#xx1oFAHDuhtMXsPlSDl6Bg). Compatible with both
Lua 5.1 and 5.2.  
   

## lk.doc

[Lubyk documentation](http://doc.lubyk.org/) parser.  
   

## LuaDoc

[http://keplerproject.github.com/luadoc/](http://keplerproject.github.com/luadoc/)  
   
 Project is no longer maintained. Successor is
[LDoc](#034qfbE9KpXhcDzXAMRulg), which is mostly compatible with LuaDoc
input.  
   

## LuaPOD

[LuaPOD](http://www.lua.inf.puc-rio.br/~sergio/luapod/) translates a POD
file into HTML using Lua and the LPeg library.  
   

## lua-ihelp

[https://github.com/dlaurie/lua-ihelp/blob/master/help.lua](https://github.com/dlaurie/lua-ihelp/blob/master/help.lua)  
   

## WebBook

[http://www.tecgraf.puc-rio.br/webbook/](http://www.tecgraf.puc-rio.br/webbook/)  
   
 WebBook will likely be the most troublesome documentation format to
deal with when consolidating documentation. It uses HTML frames, which
pose issues for indexing and searching documentation.  
