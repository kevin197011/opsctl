# frozen_string_literal: true

require "bundler/gem_tasks"
require "rubocop/rake_task"
require "git"

RuboCop::RakeTask.new

task default: :run

task :run do
  Rake::Task["rubocop"].invoke
  g = Git.open(".")
  g.add(all: true)
  g.commit_all("update.")
  g.push(g.remote("main"))
end
