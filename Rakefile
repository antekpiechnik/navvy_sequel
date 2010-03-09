require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "navvy_sequel"
    gem.summary = %Q{The sequel adapter for Navvy}
    gem.description = %Q{The sequel adapter for jkreeftmeijer\'s Navvy}
    gem.email = "antek.piechnik@gmail.com"
    gem.homepage = "http://github.com/antekpiechnik/navvy_sequel"
    gem.authors = ["Jeff Kreeftmeijer and Antek Piechnik"]
    gem.add_development_dependency "rspec"
    gem.add_development_dependency "yard"
    gem.add_dependency "navvy"
    gem.add_dependency "sequel"
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

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

task :spec => :check_dependencies

task :default => :spec

begin
  require 'yard'
  YARD::Rake::YardocTask.new
rescue LoadError
  task :yardoc do
    abort "YARD is not available. In order to run yardoc, you must: sudo gem install yard"
  end
end
