require "rake/clean"

CLEAN.include ["minitest-global_expectations-*.gem", "coverage"]

desc "Build minitest-global_expectations gem"
task :package=>[:clean] do |p|
  sh %{#{FileUtils::RUBY} -S gem build minitest-global_expectations.gemspec}
end

### Specs

desc "Run test"
task :test do
  sh %{#{FileUtils::RUBY} #{"-w" if RUBY_VERSION >= '3'} #{'-W:strict_unused_block' if RUBY_VERSION >= '3.4'} test/minitest_global_expectations_test.rb}
end

task :default=>:test

desc "Run tests with coverage"
task :test_cov do
  ENV['COVERAGE'] = '1'
  sh %{#{FileUtils::RUBY} test/minitest_global_expectations_test.rb}
end
