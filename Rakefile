require 'rubygems'
require 'rake/testtask'
require 'rake/gempackagetask'

spec = Gem::Specification.new do |s|
  s.name = "munkres"
  s.version = "0.1.0"
  s.author = "Paul Damer and Jim Wood"
  s.homepage = "http://github.com/pdamer/munkres"
  s.platform = Gem::Platform::RUBY
  s.summary = "A Ruby implementation of the Hungarian Algorithm"
  s.test_files = ['tests/munkres_test.rb']
  s.files = %w[
lib/munkres.rb
test/munkres_test.rb
README.txt
Rakefile
History.txt
]
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.need_tar = true
end

Rake::TestTask.new(:test => :build_c_ext ) do |t|
  t.libs << "test"
  t.test_files = FileList['test/*_test.rb']
  t.verbose = true
end
