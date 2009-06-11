require 'pathname'
require 'rubygems'

ROOT    = Pathname(__FILE__).dirname.expand_path
JRUBY   = RUBY_PLATFORM =~ /java/
WINDOWS = Gem.win_platform?
SUDO    = (WINDOWS || JRUBY) ? '' : ('sudo' unless ENV['SUDOLESS'])

require ROOT + 'lib/rails_datamapper/version'

AUTHOR           = 'Tom Malone'
EMAIL            = 'tomjmalone [a] gmail [d] com'
GEM_NAME         = 'rails_datamapper'
GEM_VERSION      = DataMapper::RailsDatamapper::VERSION
GEM_DEPENDENCIES = [
  [ 'dm-core',        GEM_VERSION ],
  [ 'dm-aggregates',  GEM_VERSION ],
  [ 'dm-migrations',  GEM_VERSION ],
  [ 'dm-serializer',  GEM_VERSION ],
  [ 'dm-timestamps',  GEM_VERSION ],
  [ 'dm-validations', GEM_VERSION ],
  [ 'dm-types',       GEM_VERSION ],
]

GEM_CLEAN  = %w[ pkg ]
GEM_EXTRAS = { :has_rdoc => false, :extra_rdoc_files => %w[ README.txt LICENSE TODO History.txt ] }

PROJECT_NAME = 'datamapper'
PROJECT_URL  = "http://github.com/datamapper/dm-more/tree/master/#{GEM_NAME}"
PROJECT_DESCRIPTION = PROJECT_SUMMARY = 'Rails Plugin for datamapper'

[ ROOT, ROOT.parent ].each do |dir|
  Pathname.glob(dir.join('tasks/**/*.rb').to_s).each { |f| require f }
end
