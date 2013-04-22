# Tools

  
   

## LuaDist

[LuaDist](http://luadist.org/) is a true multi-platform package
management system that provides both source and binary repository of
modules for the Lua programming language, including the handling of
dependencies.  
   

## LuaRocks

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
   

## Lua Runtime

  
   

## wxLua Front End GUI

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
   

## ZeroBrane Studio IDE

[ZeroBrane Studio](http://studio.zerobrane.com/) is a is a lightweight
Lua IDE with code completion, syntax highlighting, remote debugger, code
analyzer, live coding, and debugging support for several Lua engines.  
   
