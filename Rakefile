require 'rubygems'
require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'
require 'rake/gempackagetask'

desc 'Default: run unit tests.'
task :default => :test

desc 'Test http_configuration.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

desc 'Generate documentation for http_configuration.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'Http Configuration'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

spec = Gem::Specification.new do |s| 
  s.name = "http_configuration"
  s.version = "1.0.0"
  s.author = "Brian Durand"
  s.platform = Gem::Platform::RUBY
  s.summary = "Provide configuration options for Net::HTTP"
  s.files = FileList["lib/*"].to_a
  s.require_path = "lib"
  s.autorequire = "init.rb"
  s.test_files = FileList["{test}/**/*_test.rb"].to_a
  s.has_rdoc = true
  s.extra_rdoc_files = ["README"]
end
 
Rake::GemPackageTask.new(spec) do |pkg| 
  pkg.need_tar = true 
end