require 'pathname'

source 'http://rubygems.org'

SOURCE       = ENV.fetch('SOURCE', :git).to_sym
REPO_POSTFIX = SOURCE == :path ? ''                                : '.git'
DATAMAPPER   = SOURCE == :path ? Pathname(__FILE__).dirname.parent : 'http://github.com/datamapper'
DM_VERSION   = '~> 1.0.2'
DO_VERSION   = '~> 0.10.2'

group :runtime do

  if ENV['EXTLIB']
    gem 'extlib', '~> 0.9.15', SOURCE => "#{DATAMAPPER}/extlib#{REPO_POSTFIX}"
  end

  gem 'rails',   '~> 2.3.5'
  gem 'dm-core', DM_VERSION, SOURCE => "#{DATAMAPPER}/dm-core#{REPO_POSTFIX}"

end

group :development do

  gem 'data_objects', DO_VERSION
  gem 'do_sqlite3',   DO_VERSION
  gem 'do_mysql',     DO_VERSION
  gem 'do_postgres',  DO_VERSION
  gem 'jeweler',      '~> 1.5.2'
  gem 'rake',         '~> 0.8.7'
  gem 'rspec',        '~> 1.3.1'

end

group :quality do

  gem 'rcov',      '~> 0.9.7', :platforms => :mri_18
  gem 'yard',      '~> 0.5'
  gem 'yardstick', '~> 0.1'

end
