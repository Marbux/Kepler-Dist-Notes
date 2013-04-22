Project Charter
---------------
  
### Project goal
A cross-platform Lua4Windows replacement featuring dynamic installation of MAINTAINED (THIS NEEDS CLARIFICATION!) modules. The aim is to produce a consistent portable Lua distribution that
hopefully works well for most intentions (development, distribution, embedding, teaching, etc.)

 - Provide an easier entrance to the Lua way for newbies  
 - A complete Lua starter package: Lua runtime, some executable tools,
basic programming libraries
 - Providing a collection of documentation of the included packages  
 - Some modules will ship; others will be downloadable via the included tools.  
 - Aimed at quickly setting up an environment  
 - Executables and modules installed by default are not a complete
development environment, but a 90% starter pack  
 - it is not intended to be a roll-out package (sys-admin distribution
mechanism for many systems), but could be used that way  
 - Modules included will all be maintained.  (THIS NEEDS CLARIFICATION!!)

### Deliverables
   
 - Stand-alone executable tools included:
    - editor
    - debugger
    - package manager
    - package manager gui  
 - Default package list (to be included in distro)
 - Create standards (either develop, or as defacto by using existing)
    - Lua module manifest (so package managers can share data)
    - Preferred list of documentation tools/formats for auto-bundling
    - ???
 - Downloadable distros for the following platforms:
    - Windows
    - Linux/UNIX
    - Mac x86
 - CI environment
    - ???
 - Documentation
    - ???
    
 - Web Site
	- Relationship to existing [Kepler Project web
site](http://www.keplerproject.org/) needs to be worked out.  
 	- Need site name and domain.  
 	- _(Note that some of the following would be links whilst others would be
on-site content. Not yet in any particular order. Most of this section
is Paul Merrell's brainstorming, not consensus points.)_ 
 	- Distribution download links  
 	- Installation instructions understandable by lay users  
 	- Consolidated documentation for all shipped modules, perhaps
automatically updated by the CI server as needed  
 	- Some method to search module documentation (with frequent updates,
depending on web search engines is sub-optimal)  
 	- Tutorials  
 	- Pointers to the Lua Reference Manuals, PIL editions, and other
useful online documentation. Partly done. See [Lua Resource
Links](javascript:;).  
 	- Contact info: *e.g.,*mailing list subscription URL  
 	- Contribute HowTo  
 	- Issue tracker  
 	- Project About page  
 	- Related Projects (links)  
 	- Other?  
 - Tutorials
	- TODO  
   
    
   
### Governance
The project is governed by the project team. Whose members are;

   - Peter Drahoš
   - [Hisham Muhammad](http://hisham.hm/)
   - Steve Donovan
   - Paul Merrell
   - Andrew Starks
   - Ryan Puszta
   - [Thijs Schreijer](http://www.thijsschreijer.nl)
   - more ???, just grabbed this list of the LfW maillist

Decisions are by consensus, or in case of disputes by majority vote of the project team members. New members may be proposed by existing members, decision on new members is by the team.

### Sub-Projects and Roles

#### CI Server Admin

The CI Server sub-project is coordinated by Andrew Starks, using a new
Mac Mini that he contributed, running the [Jenkins](http://jenkins-ci.org/) extendable open source [continuous integration](http://en.wikipedia.org/wiki/Continuous_integration) server. See also [Technical Integration Coordination](#technical-integration-coordinator)  
   

#### Module Evaluation and Selection Coordinator

Ryan Puszta has been nominated without objection for the current post of
Module Evaluation and Selection Coordinator. This role makes the
decisions as to which modules will be included in the distribution.   

#### Module Policies Coordinator

Steve Donovan has been nominated without objection for the current post
of Module Policy Coordinator. This role is responsible for deciding what
tools to use, how to structure them, etc.
   
#### Technical Integration Coordinator

Peter Drahoš has been nominated without objection for the role of
technical integration coordinator. This role coordinates technical
aspects such as continuous integration, tools development, and maintains
some of the more complex builds that sometimes need to be done.  
   
> On 27 March 2013, he posted the following report on progress and
plans:  
   
> Since the discussion has stalled I decided to write up my current plans
to move things forward. Hopefully Hisham will bring some news into the
project name thread in the mean time.  
   
> There are two areas I plan to focus my attention. The first and most
important task is the setup and management of the CI server which Andrew
S. donated last week. Andrew S. has been helping me set up the CI server
so that we can now directly test all modules on multiple platforms. So
far I have done some initial burn tests to ensure the setup is stable
and works as intended, after some crashes and lockups I'm confident that
the machine will be reliable. While there is still some work to be done
on the integration with Jenkins and GitHub the current list of build
targets will be as follows:  
   
> present:  
   

> -   MinGW 4.8 32bit on Windows XP
-   MinGW 4.8 64bit on Windows 7
-   Clang 32bit + MinGW 4.7.1 on Windows 7 (experimental)
-   MSVC 2012 Decktop Edition on Windows 7
-   XCode Clang on OSX 10.8
-   XCode Clang on OSX 10.7
-   GCC 64bit on Ubuntu 12.10 64bit
-   Clang 64bit on Ubuntu 12.10 64bit

  
> planned:  
   

> -   GCC 32bit on Mint 14 32bit
-   Clang 32bit on Mint 14 32bit
-   GCC 64bit on FreeBSD
-   GCC on ARM Linux (cross compile probably)

  
> The CI process will be based on running 'luadist make' on the checked
out repositories. So the primary challenge is to make sure LuaDist is
running on all platforms. Currently only the MSVC target needs attention
and all other targets can build LuaDist just fine. CI builds on the core
modules will run daily, all other modules will only run based on git
activity.  
   
> The second step is to focus on integration between LuaDist and
LuaRocks. Here I plan to adopt the rockspec format once it is extended
to support features such as maintainers, provides and conflicts which is
essential for LuaDist. Once a unified format is agreed on LuaDist will
install all information about modules into package.path, probably into
the package.info.[name] namespace. This will allow LuaRocks and LuaDist
to look for each others packages even if require is overloaded into
LuaRocks specific paths. After this it should be possible to cleanly
provide CI services for LuaRocks too.  
   
> We still need to agree on how to store tests and documentation and how
to create and deliver reports from the CI process.  



* * * * * 

STUFF BELOW NEEDS TO BE REVIEWED AND MOVED AROUND

* * * * * 

 Clipped notes:  
   
> Steve Donovan: OK, but really highlighting that Peter's LuaDist is the
engine behind the distro. He (after all) has done the hard work of
making sure the whole thing builds everywhere.  
   
> Peter: Good summary, some of the side issues we have agreed to at least
partially address in the process is the bundling of documentation of
modules and their evaluation using an automated CI process. So basically
it is Lua4Windows replacement + dynamic installation of MAINTAINED
modules. The aim is to produce a consistent portable Lua distribution
that hopefully works well for most intentions (development,
distribution, embedding, teaching etc)  
   
   

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
   


