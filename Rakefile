require 'rspec/core/rake_task'

SPEC_DIRECTORY = '_spec'

RSpec::Core::RakeTask.new(:spec) do |task|
  task.pattern = Dir.glob("#{SPEC_DIRECTORY}/**/*_spec.rb")
  task.rspec_opts = '--color'
end

task :build do
  sh 'bundle exec jekyll build --config _config.yml,_config_en.yml --trace'
end

task :buildboth do
  sh 'bundle exec jekyll build --trace'
end

task :serve do
  sh 'bundle exec jekyll serve --config _config.yml,_config_en.yml --watch --trace --port 4000 --host 0.0.0.0'
end

task :servequick do
  sh 'bundle exec jekyll serve --config _config.yml,_config_en.yml --watch --incremental --limit_posts 3'
end

task :en do
  sh 'rm -rf _site'
  sh 'bundle exec jekyll serve --config _config.yml,_config_en.yml --watch --incremental --limit_posts 3'
end

task :es do
  sh 'rm -rf _site'
  sh 'bundle exec jekyll serve --config _config.yml,_config_es.yml --watch --incremental --limit_posts 3'
end



task :default => :spec
