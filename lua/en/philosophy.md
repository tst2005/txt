
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
