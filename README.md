# Ronin Dorks

* [Source](http://github.com/postmodern/ronin-dorks)
* [Issues](http://github.com/postmodern/ronin-dorks/issues)
* [Documentation](http://rubydoc.info/github/ronin-ruby/ronin-dorks/frames)
* [Mailing List](http://groups.google.com/group/ronin-ruby)
* irc.freenode.net #ronin

## Description

Ronin Dorks is a Ruby library for Ronin that provides support for various
Google (tm) Dorks functionality.

Ronin is a Ruby platform for exploit development and security research.
Ronin allows for the rapid development and distribution of code, exploits
or payloads over many common Source-Code-Management (SCM) systems.

### Ruby

Ronin's Ruby environment allows security researchers to leverage Ruby with
ease. The Ruby environment contains a multitude of convenience methods
for working with data in Ruby, a Ruby Object Database, a customized Ruby
Console and an extendable command-line interface.

### Extend

Ronin's more specialized features are provided by additional Ronin
libraries, which users can choose to install. These libraries can allow
one to write and run Exploits and Payloads, scan for PHP vulnerabilities,
perform Google Dorks  or run 3rd party scanners.

### Publish

Ronin allows users to publish and share code, exploits, payloads or other
data via Overlays. Overlays are directories of code and data that can be
hosted on any SVN, Hg, Git or Rsync server. Ronin makes it easy to create,
install or update Overlays.

## Features

## Synopsis

Start the Ronin console with Ronin Dorks preloaded:

    $ ronin dorks

## Examples

Google Dorks:

    #
    # Finds JBoss Seam installs.
    #
    Ronin::Dorks::GoogleDork.object do
    
      dork { query(:filetype => 'seam') }
    
    end

Custom Dorks:

    Ronin::Dorks::Dork.object do
    
      parameter :query, :description => 'The query string'
    
      dork do
        url = "http://sketchy.com/search?q=#{URI.escape(@query)}&format=txt"
        response = Net.http_get_body(:url => url)
    
        [response.lines.map { |line| line.chomp }]
      end
    
    end

## Requirements

* [gscraper](http://github.com/postmodern/gscraper) ~> 0.3.1
* [ronin](http://github.com/ronin-ruby/ronin) ~> 1.1
* [ronin-gen](http://github.com/ronin-ruby/ronin-gen) ~> 1.0
* [ronin-scanners](http://github.com/ronin-ruby/ronin-scanners) ~> 1.0

## Install

    $ sudo gem install ronin-dorks

## License

Ronin Dorks - A Ruby library for Ronin that provides support for various
Google (tm) Dorks and Hacking functionality.

Copyright (c) 2008-2011 Hal Brodigan (postmodern.mod3 at gmail.com)

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA
