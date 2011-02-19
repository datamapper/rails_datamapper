require 'pathname'

source 'http://rubygems.org'

SOURCE       = ENV['SOURCE']   ? ENV['SOURCE'].to_sym              : :git
REPO_POSTFIX = SOURCE == :path ? ''                                : '.git'
DATAMAPPER   = SOURCE == :path ? Pathname(__FILE__).dirname.parent : 'http://github.com/datamapper'
DM_VERSION   = '~> 1.0.3'
DO_VERSION   = '~> 0.10.2'

group :runtime do # Runtime dependencies (as in the gemspec)

  if ENV['EXTLIB']
    gem 'extlib', '~> 0.9.15', SOURCE => "#{DATAMAPPER}/extlib#{REPO_POSTFIX}"
  end

  gem 'rails',   '~> 2.3.5'
  gem 'dm-core', DM_VERSION, SOURCE => "#{DATAMAPPER}/dm-core#{REPO_POSTFIX}"
end

group :development do
  gem 'rake',         '~> 0.8.7'
  gem 'rspec',        '~> 1.3.1'
  gem 'jeweler',      '~> 1.5.2'
  gem 'data_objects', DO_VERSION
  gem 'do_sqlite3',   DO_VERSION
  gem 'do_mysql',     DO_VERSION
  gem 'do_postgres',  DO_VERSION
end

group :quality do
  gem 'rcov',         '~> 0.9.7', :platforms => :mri_18
  gem 'yard',         '~> 0.5'
  gem 'yardstick',    '~> 0.1'
end
