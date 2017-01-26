
Best practices in LUA ?
=======================

 * http://lua-users.org/wiki/LuaStyleGuide
 * https://luapower.com/coding-style ; https://luapower.com/philosophy
 * http://sputnik.freewisdom.org/en/Coding_Standard


My own best practices in LUA
============================

1) module definition
--------------------

 * see http://www.luafaq.org/#T1.37.2

Summary:
 * use the `require` function
 * DO NOT use the deprecated `module` function

2) version
----------

 * see http://semver.org/
 * see http://www.brandonbloom.name/blog/2013/06/19/semver/

Should I use the 'v' prefix in tag name ?
-----------------------------------------


I wonder what is the best, I'm not the first : [] http://stackoverflow.com/questions/21639437/git-flow-release-branches-and-tags-with-or-without-v-prefix

Cons

 * semver 2.0.0 drop the tagging specification and the FAQ explains ["v1.2.3" is not a semantic version](https://github.com/mojombo/semver/blob/master/semver.md#is-v123-a-semantic-version).

Pro

 * semver [1.0.0](http://semver.org/spec/v1.0.0.html#tagging-specification-semvertag) said `When tagging releases in a version control system, the tag for a version MUST be "vX.Y.Z" e.g. "v3.1.0".`
 * using the 'v' prefix allow to have extra tag.
 * the biggest git repository I known is the git kernel repository, it use the 'v' prefix and also has tag starting with extra prefix (like `gitgui-`).
 * the keplerproject's repositories seems using more prefixed-tag than not-prefixed-tag : [luasql](https://github.com/keplerproject/luasql/) [luarocks](https://github.com/keplerproject/luarocks)


My choice : I choose to use the 'v' prefix. Not hard to remove to got a valid semantic version.


3) license
----------

The main point: think about your own philosophy and write it somewhere on your profile or README ...
	
I think it's not mandatory to add a perfect License header in all files...
Think about the guy who try to search what you decide, if it found a "this project is under MIT License" he can stop to search ;)
	
 * add a comment like -- License: MIT/X11
 * or add a full LICENSE header
 * or add the full LICENSE file in your project


4) tests suite
--------------

telescope/cwtest/busted/...

5) continuous integration
-------------------------

github+travis


6) generated documentation
--------------------------

Documment your code with comment
speak about LDoc


7) distribution/release with luarocks
-------------------------------------

github+rockspecs


Other points
============

1) indentation
--------------

	You should indent your code for yourself.
	Follow your own choice (tab, 2/3/4/8 spaces ...)

	code beautifier solve this kind of debate...

2) strict
---------

 * https://luapower.com/coding-style#strict-mode

> Use `require'strict'` when developing, but make sure to remove it before publishing your code to avoid breaking other people's code.

3) syntax check
---------------

 * https://github.com/mpeterv/luacheck

4) type check
-------------

 * https://github.com/andremm/typedlua


5) class system
---------------

 * ...
