Kepler Project (redux)
========================

Toward finding consensus on the Lua Kepler Project (redux), a work in
progress.  
   

* * * * *

Table of contents
=================

-   [Contact](#jCUhpITrhJwnBvF3MA9Zuw)
-   [Project Charter](#Xf54KGWL0VryXkCRbzhfVw)
    -   [Deliverables](#Oa7AqCnTFKtjjldOyP13ww)
        -   [Distribution](#BUDlgVwbXEoGXRw3BxCcpg)
        -   [Web Site](#dFLsZYzrVfmharaNGFR1fw)
        -   [Tutorials](#1P1ii5atqZ0iHTxvZSuZiA)

    -   [Sub-Project Coodination Roles](#HfJHw32JKQWyJJyQwTXMJg)
        -   [CI Server Admin](#JX8SaGJ6KX5XplgEi94AqQ)
        -   [Module Evaluation and Selection](#2yDHCnZMAeep8tpLwDeepw)
        -   [Module Policies](#1ewQV2LxMVOinNW3s7jMww)
        -   [Technical Integration
            Coordination](#lINJfMz93On2wxex6fxsFA)

-   [Distribution Components](#F2P12HwEYkgLD9vZGXj47A)
    -   [Documentation](#O4TXysoPBjdaNqb8MP8Ilg)
        -   [DecoratorsAndDocstrings](#1bRmyViWDxma77n4NpIGHQ)
        -   [ExpLua](#QspC3UAfViJPjQ6rUM0AWQ)
        -   [LDoc](#034qfbE9KpXhcDzXAMRulg)
        -   [lk.doc](#mrlLBnGmxUHyoteq8wkhyw)
        -   [LuaDoc](#xx1oFAHDuhtMXsPlSDl6Bg)
        -   [LuaPOD](#J7PuYxWOT7tWv9zkmrBAYg)
        -   [lua-ihelp](#KCbTjPXFHPxToxjiNWdY2g)
        -   [WebBook](#rxQGrxqQJPEy51i3kp46CA)

    -   [Executables](#wl9ZuglDNg3I3F3yKbmuqw)
        -   [LuaDist](#DCtpKxoiYmc2LGx9joPVmQ)
        -   [LuaRocks](#mpnf0Mb7og9tec28DYMM0g)
        -   [Lua Runtime](#RplRUMdt8bHCleEd5oIOLQ)
        -   [wxLua Front End GUI](#HdSFzjIzmb8blMXNPON1qw)
        -   [ZeroBrane Studio IDE](#784hbs3nobCVZExJLdOMdQ)

    -   [Lua Modules](#96BX7BC01Q8PiyfVGjtraQ)
    -   [Module Manifest](#0f5UJ5zKyPevfVO9tjqUEA)

-   [New Kepler Project Web Site (drafts)](#BZtgE3nTwGtsDATySUEfrQ)
    -   [Project History](#3CGPw1Hl62aPk6DBB3g8ww)

* * * * *

Contact
-------

Report issues for Lua4Windows batteries:
[https://github.com/LuaDist/batteries](https://github.com/LuaDist/batteries)  
   
 Mailing lists:  
   

[https://groups.google.com/forum/?fromgroups=\#!forum/luaforwindows](https://groups.google.com/forum/?fromgroups=#!forum/luaforwindows)  
 [luadist@googlegroups.com](mailto:luadist@googlegroups.com)  
   

Project Charter
---------------

  
   

### Deliverables

  
   

#### Distribution

An attempt to begin consolidating consensus points (and those to which I
suspect there will be no opposition) on deliverables, derived from the
excellent summary by Thijs Schreijer.   
   
 The Distribution:  
   
 -- Provide an easier entrance to the Lua way for newbies  
   
 -- Providing a collection of documentation of the included packages  
   
 -- A complete Lua starter package: Lua runtime, some executable tools,
basic programming libraries (libraries maybe in binary or source
format)  
   
 -- Executable tools included: editor, debugger, package manager,
package manager gui  
   
 -- Some modules will ship; others will be downloadable via LuaDist and
the GUI.  
   
 -- Aimed at quickly setting up an environment  
   
 -- Works on Windows, Linux/UNIX and Mac x86 environments (although
through different downloads)  
   
 -- Executables and modules installed by default are not a complete
development environment, but a 90% starter pack  
   
 -- it is not intended to be a roll-out package (sys-admin distribution
mechanism for many systems), but could be used that way  
   
 -- Modules included will all be MAINTAINED.  
   
   
 Clipped notes:  
   
 Steve Donovan: OK, but really highlighting that Peter's LuaDist is the
engine behind the distro. He (after all) has done the hard work of
making sure the whole thing builds everywhere.  
   
 Peter: Good summary, some of the side issues we have agreed to at least
partially address in the process is the bundling of documentation of
modules and their evaluation using an automated CI process. So basically
it is Lua4Windows replacement + dynamic installation of MAINTAINED
modules. The aim is to produce a consistent portable Lua distribution
that hopefully works well for most intentions (development,
distribution, embedding, teaching etc)  
   
 Andrew S.: Peter's summary says it for me...  
 "Lua4Windows replacement + dynamic installation of MAINTAINED modules.
The aim is to produce a consistent portable Lua distribution that
hopefully works well for most intentions (development, distribution,
embedding, teaching etc)"   
   

##### Bundling of Documentation

Peter: [S]ome of the side issues we have agreed to at least partially
address in the process is the bundling of documentation of modules and
their evaluation using an automated CI process.  
   
   
 On Wed, Mar 27, 2013 at 3:48 PM, marbux \<marbux@gmail.com\> wrote:  

> Peter, on a unified format for LuaDist and LuaRocks, do you think that
> might need further metadata for purposes of classifying modules in the
> consolidated documentation?

  
 LuaDist uses short string for description of the package. LuaRocks uses
two, a short and long version. None provide keywords which would be
useful. Thats all the info you can gather from the info/rockspec
files.  
   
 Additionally LuaRocks does not install any documentation at all, it
usually installs just the lua/c modules. LuaDist by default installs to
share/[module]/doc and keeps track of the files when they are installed
in the info file. That information can be used but the files vary in
type and qulity, generally we would be better off if the documentation
was in lua module form.  
   

> I ask because you (IIRC) mentioned at some point that the CI server
> could automatically update the module documentation stored on the web
> site and because a separate download of all documentation is
> contemplated.

  
 Yes, it could do this. I can make the CI process to run ldoc/whatever
and push the output to git/githubpages on any change. So the website
could just link to it and we would only need to maintain documentation
per module. Everything else could be pushed out and re-generated
automatically.  
   

> My thought being that an alphanumeric sorted list of module names,
> each with a short one-sentence or so description, would not seem to be
> an optimal organization of consolidated documentation.

  
 This can be done now. It is related to the package manifest issue. The
short descriptions are also available on every git repository in LuaDist
which can be extracted through github api with a bit of bash-foo and
curl. The better solution is to simply have a generated manifest of all
packages that the CI server keeps up to date\*.  
   
 pd  
   
 \* I will try to generate it as soon as the CI server is set up
properly.  
   

#### Web Site

For web site candidate draft content *see* [New Kepler Project Web
Site](#BZtgE3nTwGtsDATySUEfrQ) section.  
   
 The Website:  
   
 -- Relationship to existing [Kepler Project web
site](http://www.keplerproject.org/) needs to be worked out.  
   
 -- Need site name and domain.  
   
 Note that some of the following would be links whilst others would be
on-site content. Not yet in any particular order. Most of this section
is Paul Merrell's brainstorming, not consensus points.  
   
 -- Distribution download links  
   
 -- Installation instructions understandable by lay users  
   
 -- Consolidated documentation for all shipped modules, perhaps
automatically updated by the CI server as needed  
   
 -- Some method to search module documentation (with frequent updates,
depending on web search engines is sub-optimal)  
   
 -- Tutorials  
   
 -- Pointers to the Lua Reference Manuals, PIL editions, and other
useful online documentation. Partly done. See [Lua Resource
Links](javascript:;).  
   
 -- Contact info: *e.g.,*mailing list subscription URL  
   
 -- Contribute HowTo  
   
 -- Issue tracker  
   
 -- Project About page  
   
 -- Related Projects (links)  
   
 -- Other?  
   

#### Tutorials

TODO  
   

### Sub-Project Coodination Roles

  
   

#### CI Server Admin

The CI Server sub-project is coordinated by Andrew Stark, using a new
Mac Mini that he contributed, running the
[Jenkins](http://jenkins-ci.org/) extendable open source [continuous
integration](http://en.wikipedia.org/wiki/Continuous_integration)
server.  
   
   
 Related Links:  
   
   [Module Manifest](#0f5UJ5zKyPevfVO9tjqUEA)  
   [Technical Integration Coordination](#lINJfMz93On2wxex6fxsFA)  
   

#### Module Evaluation and Selection

Ryan Puszta has been nominated without objection for the current post of
Module Evaluation and Selection Coordinator. This role makes the
decisions as to which modules will be included in the distribution.   
   

#### Module Policies

Steve Donovan has been nominated without objection for the current post
of Module Policy Coordinator. This role is responsible for deciding what
tools to use, how to structure them, *etc.*‌  
   

#### Technical Integration Coordination

Peter Drahoš has been nominated without objection for the role of
technical integration coordinator. This role coordinates technical
aspects such as continuous integration, tools development, and maintains
some of the more complex builds that sometimes need to be done.  
   
 On 27 March 2013, he posted the following report on progress and
plans:  
   
 Since the discussion has stalled I decided to write up my current plans
to move things forward. Hopefully Hisham will bring some news into the
project name thread in the mean time.  
   
 There are two areas I plan to focus my attention. The first and most
important task is the setup and management of the CI server which Andrew
S. donated last week. Andrew S. has been helping me set up the CI server
so that we can now directly test all modules on multiple platforms. So
far I have done some initial burn tests to ensure the setup is stable
and works as intended, after some crashes and lockups I'm confident that
the machine will be reliable. While there is still some work to be done
on the integration with Jenkins and GitHub the current list of build
targets will be as follows:  
   
 present:  
   

-   MinGW 4.8 32bit on Windows XP
-   MinGW 4.8 64bit on Windows 7
-   Clang 32bit + MinGW 4.7.1 on Windows 7 (experimental)
-   MSVC 2012 Decktop Edition on Windows 7
-   XCode Clang on OSX 10.8
-   XCode Clang on OSX 10.7
-   GCC 64bit on Ubuntu 12.10 64bit
-   Clang 64bit on Ubuntu 12.10 64bit

  
 planned:  
   

-   GCC 32bit on Mint 14 32bit
-   Clang 32bit on Mint 14 32bit
-   GCC 64bit on FreeBSD
-   GCC on ARM Linux (cross compile probably)

  
 The CI process will be based on running 'luadist make' on the checked
out repositories. So the primary challenge is to make sure LuaDist is
running on all platforms. Currently only the MSVC target needs attention
and all other targets can build LuaDist just fine. CI builds on the core
modules will run daily, all other modules will only run based on git
activity.  
   
 The second step is to focus on integration between LuaDist and
LuaRocks. Here I plan to adopt the rockspec format once it is extended
to support features such as maintainers, provides and conflicts which is
essential for LuaDist. Once a unified format is agreed on LuaDist will
install all information about modules into package.path, probably into
the package.info.[name] namespace. This will allow LuaRocks and LuaDist
to look for each others packages even if require is overloaded into
LuaRocks specific paths. After this it should be possible to cleanly
provide CI services for LuaRocks too.  
   
 We still need to agree on how to store tests and documentation and how
to create and deliver reports from the CI process.  
   

Distribution Components
-----------------------

  
   

### Documentation

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
   

#### DecoratorsAndDocstrings

[DecoratorsAndDocstrings](http://lua-users.org/wiki/DecoratorsAndDocstrings) has
methods for associating documentation with objects at runtime.  
   

#### ExpLua

[ExpLua](http://lua-users.org/wiki/ExpLua) is both a code comment format
and a tool for extracting said comments and exporting HTML, LaTeX, and
whatnot. It is freely available for use under the same License as the
Lua project, with the usual disclaimers.  
   

#### LDoc

[https://github.com/stevedonovan/LDoc](https://github.com/stevedonovan/LDoc)  
   
 Successor to [LuaDoc](#xx1oFAHDuhtMXsPlSDl6Bg). Compatible with both
Lua 5.1 and 5.2.  
   

#### lk.doc

[Lubyk documentation](http://doc.lubyk.org/) parser.  
   

#### LuaDoc

[http://keplerproject.github.com/luadoc/](http://keplerproject.github.com/luadoc/)  
   
 Project is no longer maintained. Successor is
[LDoc](#034qfbE9KpXhcDzXAMRulg), which is mostly compatible with LuaDoc
input.  
   

#### LuaPOD

[LuaPOD](http://www.lua.inf.puc-rio.br/~sergio/luapod/) translates a POD
file into HTML using Lua and the LPeg library.  
   

#### lua-ihelp

[https://github.com/dlaurie/lua-ihelp/blob/master/help.lua](https://github.com/dlaurie/lua-ihelp/blob/master/help.lua)  
   

#### WebBook

[http://www.tecgraf.puc-rio.br/webbook/](http://www.tecgraf.puc-rio.br/webbook/)  
   
 WebBook will likely be the most troublesome documentation format to
deal with when consolidating documentation. It uses HTML frames, which
pose issues for indexing and searching documentation.  
   

### Executables

  
   

#### LuaDist

[LuaDist](http://luadist.org/) is a true multi-platform package
management system that provides both source and binary repository of
modules for the Lua programming language, including the handling of
dependencies.  
   

#### LuaRocks

[LuaRocks](http://luarocks.org/)

is a deployment and management system for Lua modules.

  
  LuaRocks allows you to install Lua modules as self-contained packages
called "rocks", which also contain version dependency information. This
information is used both during installation, so that when one rock is
requested all rocks it depends on are installed as well, and at run
time, so that when a module is required, the correct version is loaded.
LuaRocks supports both local and remote repositories, and multiple local
rocks trees.

  

  
 Note Hisham's 24 March 2013 announcement on Lua-L:   
   
 I'm happy to announce we just reached 250 entries in the LuaRocks  
 repository (that's 250 different things for which you can run  
 'luarocks install thing'). Counting multiple versions of projects,  
 that totals 739 rockspecs so far.  
   

#### Lua Runtime

  
   

#### wxLua Front End GUI

Steve Donovan: "I think what we need to do is collect the LfW docs and
example trees into a separate repo, and then Peter can merge that into
his zip.  
   
 I've started making a manifest of all the LuaDist packages that are
binary compatible - the batteries have about 70 odd, but there's nearly
100 other packages that can be directly installed from the batteries
with 'luadist install' (note: this doesn't require a compiler, CMake or
git to be installed) So I've started adding tags to this manifest file,
and then I can write a little wxLua app which will allow users to
download (and \_upgrade\_) any other compatible LuaDist package."  
   
 Add keyword search, as suggested by Andrew?  
   
 Integrate the wxLua app with ZeroBrane Studio?  
   
 Peter on Lua version compatibility:   
   
 LuaDist determines compatibility by walking the dependency list of the
package being evaluated. This goes on for any package, not just Lua
modules. All Lua modules have a dependency on Lua marked in their
dist.info[1] which is used to check what Lua version it is compatible
against. For source modules this works flawlessly but binaries are
trickier as modules also need to know what ABI they were compiled
against, that is currently not implemented but it is already worked on.
Additionally modules that are known to be conflicting against other
modules can be marked so [2].  
   
 Any module can be quickly evaluated against the list of installed
packages to determine if it is compatible with the current setup, so the
answer to your question is yes. However, we can not currently generate
binaries for modules that are both Lua 5.1 and 5.2 compatible because of
the above mentioned issue. So for now only Lua 5.1 binaries are
available.  
   
 Steve can access all the required functionality through the "dist"
module which can be required from Lua directly. This includes functions
that evaluate compatibility of the module against already deployed
modules [3]. Required dist metadata is only "name" and "version"
everything else is optional and any other entries can be present,
however all Lua modules also contain dependency "depends = { lua ..
}".  
   
 All Steve will need to display is a list of modules and their versions
with a checkbox indicating if it can be installed into the current
destination. Better yet it could use a simple option "filter by
compatibility [x]" so you can hide incompatible modules and versions.  
   
 [1]
[https://github.com/LuaDist/luajit/blob/master/dist.info\#L18](https://github.com/LuaDist/luajit/blob/master/dist.info#L18)
- Marks LuaJIT conflict with lua (they share liblua.so)  
 [2]
[https://github.com/LuaDist/luafilesystem/blob/master/dist.info\#L13](https://github.com/LuaDist/luafilesystem/blob/master/dist.info#L13)
- Marks luafilesystem compatible witj lua 5.1 and above  
 [3]
[https://github.com/LuaDist/luadist-git/blob/master/dist/init.lua\#L71](https://github.com/LuaDist/luadist-git/blob/master/dist/init.lua#L71)
- Dependency check in the install command uses "dist.depends" module  
   

#### ZeroBrane Studio IDE

[ZeroBrane Studio](http://studio.zerobrane.com/) is a is a lightweight
Lua IDE with code completion, syntax highlighting, remote debugger, code
analyzer, live coding, and debugging support for several Lua engines.  
   

### Lua Modules

See thread, What packages should be in the base install?,
[https://groups.google.com/group/luaforwindows/browse\_thread/thread/55d898bc35f6e09c/011a14201ceb5201](https://groups.google.com/group/luaforwindows/browse_thread/thread/55d898bc35f6e09c/011a14201ceb5201).
  
   
   
 About 70 that LuaDist currently installs automatically; another 100 or
so that can be pulled in. -- Steve D.  
   

### Module Manifest

Peter S. "Generating and keeping a manifest of modules will be
essential. This came up multiple times in the discussions. For this we
need the [[continuous
integration](http://en.wikipedia.org/wiki/Continuous_integration)]
server (contributed by Andrew Stark) which could generate it and keep it
up to date (perhaps using a github gist so it does not need to serve
it).  
   
 "This would open up some possibilities LuaDist currently cannot do
efficiently. Eg. error help on require when packages are missing could
point users to download the missing package using Michal Kottmans
intellua. Steve already mentioned the wx based GUI frontend to the
installer which could even integrate with ZeroBrane. Keyword search as
suggested by Andrew etc. All these would rely on it so it makes sense to
start with the manifest."  
   
 Steve D.
"[https://gist.github.com/stevedonovan/5262203](https://gist.github.com/stevedonovan/5262203)  
   
 "This is the result of parsing the output of 'luadist show' for all  
 modules (I'm sure there's a more scientific way). If a package does  
 not have a 'Windows-x86' then it's not included. (There are some  
 packages, like cd-examples, which are pure Lua but marked as  
 'universal-binary')  
   
 "I've started adding tags to the records - basically this is what the  
 proposed GUI tool will use.  
   
 "(the parsing script is a real hack)"  
   

New Kepler Project Web Site (drafts)
------------------------------------

### Project History

**TODO: Add history of LFW.**  
   
 The Kepler project is the melding of several prior [Lua programming
language](http://www.lua.org) projects: [i] the former [Kepler
Project](http://www.keplerproject.org/); [ii] the Kepler Project's
outgrowth, the [LuaForge
Project](http://luaforge.net/projects/http://luaforge.net/projects/);
[iii] the [Lua for Windows
Project](https://code.google.com/p/luaforwindows/\); and [iv] a host of
individual executables and Lua modules developed by a multitude of Lua
community members.  
   
 In accord with the meaning of Lua in Portuguese ("the Moon"), the
original Lua Kepler Project drew its name from Johannes Kepler
(1571-1630), the founder of celestial mechanics. *See* [Johannes Kepler:
His Life, His Laws and
Times](http://kepler.nasa.gov/Mission/JohannesKepler/).  
   
 Here is a lightly edited history of the former Kepler and LuaForge
projects by one of its [remaining
contributors](http://www.keplerproject.org/en/Dev_Team), [Hisham H.
Muhammad](http://hisham.hm/about):   
   

> The former Kepler Project was envisioned by [André
> Carregal](http://br.linkedin.com/in/andrecarregal) as a research
> project to make Lua a viable language for web development, in the
> sense that things like PHP and Ruby are nowadays viable, ie, having
> the tools so that a coder can concentrate on their app rather than
> reinventing wheels. So yeah, that goal included a good deal of the
> "batteries" as well as figuring out distribution issues.   
>    
>  A major part of this project, also, was to bring together people who
> were working seperately in pieces of this puzzle, including the
> politics to cooperate with pre-Kepler projects such as CGILua,
> LuaSocket and LuaBinaries. This also included getting funding --
> Carregal spent a lot of time working to get government grants for the
> research project (which was officially a project involving PUC-Rio and
> the company he worked on as well).   
>    
>  People like Fabio and myself (both grad students under Roberto at the
> time) were funded by this project to work on Lua modules. LuaRocks was
> created because of Kepler, and I was paid to work on it for two years.
> LuaForge was also created and its maintenance funded by Kepler.
> Eventually, we didn't get a grant renewal, plus the overall landscape
> wasn't much in Kepler's favor (it never took off as a killer app for
> Lua), and the project mostly died off.   
>    
>  Some of us "inherited" the modules we worked on and remained on them
> as volunteer side-projects, working on our free time. I kept LuaRocks,
> Fabio kept Orbit and others, and so on. Note that this includes stuff
> that I perceive as key infrastructure such as LuaFileSystem. Fabio
> takes care of its github repo, and released version 1.6.2 about 6
> months ago.   
>    
>  André Carregal, on the other hand, effectively left the project (and
> I really can't blame him for the burnout, after all the effort he went
> through -- he's an unsung hero of the Lua ecosystem (or perhaps
> "sung", since [Yuri's book](http://codingplaces.net/), which I
> heartily recommend for insights on the story)). The project was
> reshaped not as a platform that made "releases" but as a general hub
> for all those subprojects (the availability of LuaRocks helped to
> diminished the reliance on one big tarball).  
>    
>  The LuaForge shutdown was probably the major effect of the project's
> twilight. Carregal tried as best as he could to keep the service
> going, but without funding to hire someone to babysit GForge (and the
> growing expectations of the Lua userbase), keeping it up with regular
> shortages wasn't an option. He tried handing over LuaForge to "the
> community", but as most of us remember, lots and lots of discussion
> went on, but nothing as concrete as the old LuaForge ever emerged.

  
