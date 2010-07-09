require 'rubygems'
require 'bundler'

begin
  Bundler.setup(:development, :doc)
rescue Bundler::BundlerError => e
  STDERR.puts e.message
  STDERR.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end

require 'rake'
require 'jeweler'
require './lib/ronin/dorks/version.rb'

Jeweler::Tasks.new do |gem|
  gem.name = 'ronin-dorks'
  gem.version = Ronin::Dorks::VERSION
  gem.license = ['GPL-2']
  gem.summary = %Q{A Ruby library for Ronin that provides support for various Google (tm) Dorks functionality.}
  gem.description = %Q{Ronin Dorks is a Ruby library for Ronin that provides support for various Google (tm) Dorks functionality.}
  gem.email = 'postmodern.mod3@gmail.com'
  gem.homepage = 'http://github.com/ronin-ruby/ronin-dorks'
  gem.authors = ['Postmodern']
  gem.has_rdoc = 'yard'
end

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new
task :default => :spec

require 'dm-visualizer/rake/graphviz_task'
DataMapper::Visualizer::Rake::GraphVizTask.new(
  :bundle => [:runtime],
  :include => ['lib'],
  :require => ['ronin/scanners']
)

require 'yard'
YARD::Rake::YardocTask.new
