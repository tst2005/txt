# Comment comparer les languages ?

 * des languages ? ok regardons du coté de [githut](http://githut.info/)
 * [avec des benchmarks ?](http://benchmarksgame.alioth.debian.org/) si on parle de perf et d'utilisation de mémoire alors parlons de [LuaJIT](http://luajit.org/performance.html)
 * Comprendre pourquoi il n'y a pas/plus de comparaison Lua VS LuaJIT sur alioth depuis [2011](http://lua-users.org/lists/lua-l/2011-07/msg00059.html) il me semble que l'argument etait LuaJIT est pas finit(compatible avec Lua 5.1, ce qui est le cas maintenant, mais pas non plus compatible avec Lua 5.3 evidement...) visiblement je ne suis pas le seul à [chercher pourquoi](https://attractivechaos.wordpress.com/2011/04/23/no-luajit-in-the-computer-language-benchmarks-game/)
 * Des trace d'article montrant que LuaJIT était plus rapide que [Javascript V8](https://www.quora.com/Why-is-LuaJIT-faster-than-V8?share=1) ou [comparé à C/C++](http://lua-users.org/lists/lua-l/2010-08/msg00667.html) ; [pourquoi luaJIT est si rapide](https://www.quora.com/What-makes-LuaJIT-faster-than-Lua)


# Qui et où est utilisé le Lua ?

Je n'ai pas trouvé de listing très joli, mais il y a de quoi explorer :

 * [lua-users.org LuaUses](http://lua-users.org/wiki/LuaUses)
 * [lua.org uses](http://www.lua.org/uses.html)
 * [wikipedia Applications](https://en.wikipedia.org/wiki/Lua_%28programming_language%29#Applications)
 * [where-lua-is-used by marbux](https://sites.google.com/site/marbux/home/where-lua-is-used)
 * [where-luajit-is-used](http://wiki.luajit.org/where-luajit-is-used)

# Fait/maintenu par qui ?

 * Lua (officiel) evolue de facon assez fermée ...
 * LuaJIT évolue grace a Mike Pall depuis plus de 10 ans (qui bénéficie de gros sponsor/contributeur) mais c'est en passe de changer : http://www.freelists.org/post/luajit/Looking-for-new-LuaJIT-maintainers

# Listé par mes soins

## du web :

 * nginx / [openresty.org](http://openresty.org/)
 * mais aussi apache+mod_lua et lighttpd
 * [haproxy](http://www.arpalert.org/src/haproxy-lua-api/1.6/index.html)
 * [Lwan Web Server](https://github.com/lpereira/lwan)
 * [pegasus](http://evandrolg.github.io/pegasus.lua/)

## game dev
 * [love2d.org](https://love2d.org/) / [love3dd](https://github.com/excessive/love3d)
 * [skynet](https://github.com/cloudwu/skynet)
 * (moins connu : http://www.cocos2d-x.org avec binding lua et js)
 * ...

## other
 * awesome : Window manager
 * [prosody](http://prosody.im/) : XMPP Server
 * [luakit.org](http://luakit.org/), ([github](https://github.com/mason-larobina/luakit)) : Web Browser

# Les outils incluant du Lua comme plug-in

 * World of Warcraft, [minecraft](http://www.computercraftedu.com/), [roblox](http://www.roblox.com/)/[github](https://github.com/ROBLOX/Core-Scripts) et pleins d'autres jeux...
 * SQL DB: postgres
 * NoSQL DB: redis
 * NoSQL DB manager : [Tarantool](https://en.wikipedia.org/wiki/Tarantool) [2](https://github.com/tarantool/tarantool/) (fait par mail.ru) ; [article nginx+tarantool+redis](http://highscalability.com/blog/2016/2/17/building-nginx-and-tarantool-based-services.html)
 * snort, nmap, [suricata-ids](http://suricata-ids.org/features/all-features/)([doc](https://redmine.openinfosecfoundation.org/projects/suricata/wiki/Lua_scripting))

Les moins connus (avec un support et une doc souvent déplorable) :

 * (plugin) alephone
 * (plugin) teamspeak3
 * (plugin) firefox?

# Quelques projets exotiques marquant 

Toujours marrant à placer dans la discussion :

 * dans le kernel linux pour débugger [ktap.org](http://ktap.org) ou [sur github](https://github.com/ktap/ktap) [depuis le kernel 3.13](https://linuxfr.org/news/sortie-de-linux-3-13#ktap) ou [loski](https://github.com/renatomaia/loski)
 * dans le kernel NetBSD pour controler le reseau [NPFLua](https://www.netbsd.org/gallery/presentations/lneto/eurobsdcon14.pdf), [Lua Kernel Scripting](http://www.phoronix.com/scan.php?page=news_item&px=NetBSD-7.0-Released)
 * dans Adobe Photoshop Lightroom [site officiel](https://www.adobe.com/devnet/photoshoplightroom.html) voir [article](http://www.paulrohde.com/lightroom-and-lua/) et des [goodies](http://regex.info/blog/lightroom-goodies)
 * conky
 * [LuCI](http://wiki.openwrt.org/doc/techref/luci) le serveur web de configuration d'OpenWRT
 * MediaWiki (ah bon?)
 * nmap, snort, [wireshark](https://wiki.wireshark.org/Lua)
 * [ZeroBrane Studio](https://en.wikipedia.org/wiki/ZeroBrane_Studio) un IDE en Lua
 * [Geany](http://geany.org/) un IDE, [plugins](https://github.com/geany/geany-plugins/)/[lua](https://github.com/geany/geany-plugins/tree/master/geanylua), [scripts lua](http://wiki.geany.org/config/scripts/lua)
 * [vim lua-ftplugin](https://github.com/xolox/vim-lua-ftplugin)
 * [vis](https://github.com/martanne/vis) : un editeur vi-like avec support lua
 

Des moins aboutis mais ca existe :

 * [PacketScript](https://github.com/dergraf/PacketScript) pour controler netfilter via lua (en kernelspace) ou [netfilter-lua](https://github.com/sam-github/netfilter-lua) (en userspace), trouvé [ici](http://lua-users.org/lists/lua-l/2012-06/msg00018.html)
 * [pf in lua](https://github.com/Igalia/pflua)
 * ...

# les grands

 * multipathnet de facebook : https://github.com/facebookresearch/multipathnet
 * les autres projets de facebook : ...
 * [mscoco](http://mscoco.org/) de microsoft (sur [github](https://github.com/pdollar/coco)) FIXME est-ce que MS utilise vraiment du lua dans mscoco ?!


# Les inconvenients et problèmes du Lua

Il y a de quoi critique!

Certain finisse [par abandonner](https://www.demelierdavid.fr/index.php?post/index.php/arret-de-lua/)

# les problèmes globaux

# trouver la meilleure solution tierce

En lua j'ai tendance a dire qu'on a plus vite fait de recoder soit meme que de trouver quelque chose d'existant qui correspondent a ses besoins.
Du coup on se retrouve avec une tonne d'implementation qui répondent au meme besoin, mais de facon toujours un peu différente, et souvent totalement incompatible entre elles...

Exemple: celui du [support pour json](http://lua-users.org/wiki/JsonModules)

Illustration de rigeure : https://xkcd.com/927/

# Les problemes techniques

## Les APIs qui changent a chaque version

parfois pour améliorer les choses mais
... souvent et pas toujours pour des raisons très logiques.

Voir: `unpack` VS `table.unpack` (pourquoi `pairs`, `ipairs`, ... sont pas dans `table.*` alors ? je crois que jai compris pourquoi, parce qu'ils ont aussi ajouté `string.unpack` mais bon ...)

Voir: string.gfind -> string.gmatch (Lua 5.0 a 5.1)
Voir: table.foreach/table.foreachi -> for + pairs/ipairs

Le vrai problème n'est pas que les APIs changent, mais qu'il gère très mal les transitions...
Les couches de compatibilités sont fournie pas la suite (par la communauté?)

* setfenv/getfenv/loadstring VS _ENV/load/...
* module()
* ...


## la bonne facon de definir un module

* ne pas utiliser la fonction `module()`
* Avoid globals in modules


## charger et utiliser un module

`local foo = require "foo"`


## pas de support officiel pour des besoins classiques

 * UTF-8 :
solution partielle en lua : [la mienne : lua-utf8](https://github.com/tst2005/lua-utf8) ou [une autre : lua-utf8-simple](https://github.com/blitmap/lua-utf8-simple) ;
solutions complète (nécessite compilation) : [luautf8](https://github.com/starwing/luautf8) (luarocks will help you).
 * FileSystem : ... lua-filesystem(aka lfs) [les alternatives](http://lua-users.org/wiki/FileSystemOperations) (il y aussi luaposix)
 * Socket/Network : ... lua-socket (aucune autre alternative? si il y a un fork mieux maintenu pour lua 5.2/5.3 et aussi luaposix.socket)
 * BitWise Operation : lua5.2/bit32 luajit/bit [in lua](https://github.com/davidm/lua-bit-numberlua)
 * RegExp : ...
 * Crypto : ... [luasec](https://github.com/brunoos/luasec), [luaoss](https://github.com/wahern/luaossl)
 * JSON : [lunajson](https://github.com/grafi-tt/lunajson), cjson, dkjson, ...
 * XML : expat, [SLAXML](https://github.com/Phrogz/SLAXML), ...
 * SQL : [luasql](https://github.com/keplerproject/luasql), luadbi
 * de/compression : ...
 * Command-line parsing : ... lua_cliargs, alt-getopt, ...
 * shell sub-process : ... luabash, luash, luaposix+popen3.lua, ...
 * ...

Solution: voir du coté de [penligth (aka pl)](https://github.com/stevedonovan/Penlight), ...
http://lua-users.org/wiki/ModuleReview

## ne parlons meme pas des threads




## parcourir des tables avec des trous

Solution (non testée): [lua-multikey](https://github.com/siffiejoe/lua-multikey/) voir sa [doc](http://siffiejoe.github.io/lua-multikey/)


## le parser/lexer

La version 5.2 a introduit la notion de `label` et `goto`.
Le mot goto est devenu réservé. On ne peux plus l'utiliser comme nom de variable.
Ca n'affecte pas le contenu des tableaux.

On ne peux plus faire 

`local t = {}; t.goto = 123`

ou

`local t = { goto = 123 }`

On peux toujours faire
`local t = {} ; t["goto"] = 123`
ou
`local t = { ["goto"] = 123 }`

On voit bien que ce n'est pas un probleme de fond mais de forme.
Le parseur(?)/lexer(?) n'est pas assez intelligent pour faire la différence entre un token qui est le mot réservé de celui qui ne l'est pas (valeure d'un element d'une table)

# problemes divers

## testsuite ?

meme les outils de tests sont nombreux ...

 * [busted](https://github.com/Olivine-Labs/busted), [doc](http://olivinelabs.com/busted/#overview)
 * [telescope](https://github.com/norman/telescope)
 * luassert
 * cwtest
 * ...

# en vrac, a trier

 * [une présentation du workshop lua 2013](http://files.catwell.info/presentations/2013-11-lua-workshop-lua-ecosystem/?full#cover)
voir [la page 19](http://files.catwell.info/presentations/2013-11-lua-workshop-lua-ecosystem/?full#19) (nombre de modules: ruby 66k, pypi 36.5k, cpan 28.7k, luarocks 330)
 * packet lua chez debian : [info](https://alioth.debian.org/projects/pkg-lua/) ; [regle et politique](http://pkg-lua.alioth.debian.org/policy.html)
 * [lua rocks](http://lua-users.org/wiki/LuaRocks) ; [config](http://lua-users.org/wiki/LuaRocksConfig)
[create](https://github.com/keplerproject/luarocks/wiki/Creating-a-rock) ;
[install](https://github.com/keplerproject/luarocks/wiki/Installation-instructions-for-Unix) ;
[use](https://github.com/keplerproject/luarocks/wiki/Using-LuaRocks) ;
[doc](https://github.com/keplerproject/luarocks/wiki/Documentation#Support__more_resources) ;
 * [lua dist](http://lua-users.org/wiki/LuaDist)
 * [lua-toolbox](https://lua-toolbox.com/)
 * [webrocks](http://lua-users.org/wiki/WebRocks)
 * [luapower](https://luapower.com/) [github](https://github.com/luapower/)
 * [profiling lua with kcachegrind](http://jan.kneschke.de/projects/misc/profiling-lua-with-kcachegrind/)

# Divers projets avec du lua

* [irccd](https://linuxfr.org/news/irccd-le-robot-irc-scriptable-en-lua-grandit) : un bot irc en C++/Lua
* à propos de securité avec [LuaJIT](http://stackoverflow.com/questions/4911762/why-is-luajit-so-good/4911818#4911818)
* [ravi](https://github.com/dibyendumajumdar/ravi) et ses [perfs](http://the-ravi-programming-language.readthedocs.org/en/latest/ravi-benchmarks.html) : Du lua compilé avec LLVM
* underscore :
[doc](http://mirven.github.io/underscore.lua/) /
[github](https://github.com/mirven/underscore.lua) (underscore.lua is obsolete ?) ; Moses seems more up-to-date : [doc](http://yonaba.github.io/Moses/) [github](https://github.com/Yonaba/Moses)
* strong

# Les environements web avec du lua

Voir l'article http://ophal.org/content/30 qui compare :

 * [Lapis](http://leafo.net/lapis/)
 * [Ophal](http://ophal.org/)
 * [Sailor](http://sailorproject.rg/)
 * [Turbo.lua](http://www.turbolua.org/)

il existe aussi :

 * [Lusty](https://github.com/Olivine-Labs/lusty)
 * [Tir](http://tir.mongrel2.org/)
 * [Luvit](https://luvit.io/)

Pour les API REST :

 * [Spore](https://github.com/SPORE/)
 * [AWS](https://github.com/umegaya/lua-aws)


# pour moi meme

 * coding style : https://luapower.com/coding-style
