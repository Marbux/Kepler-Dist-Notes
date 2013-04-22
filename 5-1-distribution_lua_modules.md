# Lua Modules

See thread, What packages should be in the base install?,
[https://groups.google.com/group/luaforwindows/browse\_thread/thread/55d898bc35f6e09c/011a14201ceb5201](https://groups.google.com/group/luaforwindows/browse_thread/thread/55d898bc35f6e09c/011a14201ceb5201).
  
   
   
 About 70 that LuaDist currently installs automatically; another 100 or
so that can be pulled in. -- Steve D.  
   

## Module Manifest

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
   
