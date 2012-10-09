require "rubygems"
require "bundler/setup"

require 'active_record'
require 'sqlite3'

desc "Migrate the database through scripts in db/migrate."
task :migrate do
  ActiveRecord::Base.establish_connection(YAML.load(File.read(File.join('.','database.yml')))[ENV['ENV'] ? ENV['ENV'] : 'development'])
  ActiveRecord::Migrator.migrate("db/migrate/")
end
