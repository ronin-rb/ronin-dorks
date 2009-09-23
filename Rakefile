# -*- ruby -*-

require 'rubygems'
require 'hoe'
require 'hoe/signing'
require './tasks/spec.rb'
require './tasks/yard.rb'

Hoe.spec('ronin-dorks') do
  self.rubyforge_name = 'ronin'
  self.developer('Postmodern', 'postmodern.mod3@gmail.com')
  self.remote_rdoc_dir = 'docs/ronin-dorks'
  self.extra_deps = [
    ['ronin', '>=0.3.0'],
    ['gscraper', '>=0.2.2']
  ]

  self.extra_dev_deps = [
    ['rspec', '>=1.1.12'],
    ['yard', '>=0.2.3.5']
  ]

  self.spec_extras = {:has_rdoc => 'yard'}
end

# vim: syntax=Ruby
