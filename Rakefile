require 'rubygems'
require 'rake'

desc 'Default: run unit tests.'
task :default => :test

begin
  require 'rspec'
  require 'rspec/core/rake_task'
  desc 'Run the unit tests'
  RSpec::Core::RakeTask.new(:test)
rescue LoadError
  task :test do
    STDERR.puts "You must have rspec 2.0 installed to run the tests"
  end
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "http_configuration"
    gem.summary = %Q{Gem that provides the ability to set defaults for proxies and timeouts for Net::HTTP.}
    gem.description = %Q(Gem that provides the ability to set defaults for proxies and timeouts for Net::HTTP. Simplifies integration of HTTP calls into any environment and provides a unified interface for setting values.)
    gem.email = "brian@embellishedvisions.com"
    gem.homepage = "http://github.com/bdurand/http_configuration"
    gem.authors = ["Brian Durand"]
    gem.rdoc_options = ["--charset=UTF-8", "--main", "README.rdoc"]
    
    gem.add_development_dependency('rspec', '>= 2.0.0')
    gem.add_development_dependency('jeweler')
  end

  Jeweler::GemcutterTasks.new
rescue LoadError
end
