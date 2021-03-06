
__NOTE: kiwi is no longer supported, please use npm. This repository will remain for educational purposes only__ 

# Kiwi - Node.js Package Management

  JavaScript package management system for **node.js**
## About

Kiwi development is sponsored by [Vision Media](http://vision-media.ca) and hosting
is sponsored by [Slicehost](http://slicehost.com).
  
## Features

  * Fast / Solid
    - Written in bash script
    - Utilizes battle-tested programs
  * Packaging of "seeds" (tarballs)
    - Ignores .{git,svn,cvs}
    - Ignores globs in .ignore when packing
  * Distributed packages as "seeds"
    - installation (including node and kiwi itself)
    - installation of local seeds
    - uninstallation
    - updating
    - publishing to the kiwi seed server (similar to gemcutter for RubyGems)
    - listing of installed seeds and their versions
    - searching of remote seeds
    - arbitrary build commands (so you can make, scons, jake, etc)
    - installation via flat-list of seeds and associated versions
    - collects stats such as seed download counts
    - user registration via command-line
    - user authentication
  * Version resolution
    - via installation
    - via runtime
  * Interactive console or REPL
    - Auto-detects and utilizes rlwrap
  * Multiple environments
    - Use one or more environments to manage your seeds
  * Not dependant on GIT (like most other proposed node package managers)
  
## Kiwi Vs Others

Other node package management systems utilize absolute urls
in order to fetch their tarballs, below is an example of
both **kiwi** and **npm** installing the same library.

kiwi:

    $ kiwi install haml
    
npm:
    
    $ npm install http://github.com/creationix/haml-js/tarball/0.1.2
  
## Installation

Download kiwi or clone the repo and run:

    $ [sudo] make install
    
Or if you have [homebrew](http://github.com/mxcl/homebrew) installed
you can simply run:

    $ [sudo] brew install kiwi

## Uninstallation

    $ [sudo] make uninstall
    
## Updating 

    $ [sudo] kiwi update
    
## Example Walkthrough

First we need to install a few seeds:
    $ kiwi install haml
    $ kiwi install class
    
Now we can create a file named _app.js_ anywhere
on our system and add:

    var kiwi = require('kiwi'),
        sys = require('sys')
    
    sys.p(kiwi.require('haml', '>= 0.0.1'))
    sys.p(kiwi.require('haml', '= 0.4.0'))
    sys.p(kiwi.require('class'))
    
Then run it with node:
    $ node app.js

## Testing

Specs are run using Ruby RSpec's `spec` executable.
  
    $ make test
    
## Dependencies

Command dependencies are as follows:

  * sed
  * awk
  * tar
  * egrep
  
Currently tested with:
  
  * MacOS 1.5.8
  * GNU bash, version 3.2.17(1)-release (i386-apple-darwin9.0)
  * tar (GNU tar) 1.15.1
  * curl 7.16.3
  * egrep (GNU grep) 2.5.1
  
## More Information

  * [Overview Blog Article](http://tjholowaychuk.com/post/537372859/nodejs-package-manager)
  
## License 

(The MIT License)

Copyright (c) 2009 TJ Holowaychuk &lt;tj@vision-media.ca&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.