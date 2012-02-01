require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  gem.name = "skles"
  gem.summary = %Q{Ruby interface for SKLES (StrongKey Light Encryption System) boxes}
  gem.description = %Q{A Ruby wrapper around the StrongKey Lite SOAP client API (Ruby < 1.9 compat fork).}
  gem.email = "git@timothymorgan.info"
  gem.homepage = "http://github.com/isaacfeliu/skles"
  gem.authors = [ "Tim Morgan" ]
  gem.required_ruby_version = '>= 1.8'
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new

require 'yard'
YARD::Rake::YardocTask.new('doc') do |doc|
  doc.options << "-m" << "textile"
  doc.options << "--protected"
  doc.options << "--no-private"
  doc.options << "-r" << "README.textile"
  doc.options << "-o" << "doc"
  doc.options << "--title" << "Ruby SKLES Documentation".inspect

  doc.files = [ 'lib/**/*', 'README.textile' ]
end

task(:default => :spec)
