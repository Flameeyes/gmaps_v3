require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "gmaps_v3"
    gem.summary = %Q{GMaps v3 enable simple integration with Google Maps API v3}
    gem.description = %Q{API to simple do requests on Google Maps API V3}
    gem.email = "wilkerlucio@gmail.com"
    gem.homepage = "http://github.com/wilkerlucio/gmaps_v3"
    gem.authors = ["Wilker Lucio"]
    gem.add_dependency 'simplehttp', '>= 0.1.3'
    gem.add_dependency 'json', '>= 1.2.4'
    gem.add_development_dependency "rspec", ">= 1.2.9"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new

  task :spec => :check_dependencies
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

begin
  require 'spec/rake/spectask'
  Spec::Rake::SpecTask.new(:spec) do |spec|
    spec.libs << 'lib' << 'spec'
    spec.spec_files = FileList['spec/**/*_spec.rb']
  end

  Spec::Rake::SpecTask.new(:rcov) do |spec|
    spec.libs << 'lib' << 'spec'
    spec.pattern = 'spec/**/*_spec.rb'
    spec.rcov = true
  end

  task :default => :spec
rescue LoadError
  puts "RSpec (or a dependency) not available. Install it with: gem install rspec"
end

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "gmaps_v3 #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
