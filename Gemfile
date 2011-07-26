source "http://rubygems.org"

# Specify your gem's dependencies in typus.gemspec
gemspec

# Yes, some dependencies are in typus.gemspec, but it's a little bit difficult
# to mantain the above code there. I'll keep here for the moment ...

gem 'acts_as_list'
gem 'acts_as_tree'

# ASSET SUPPORT
# TODO - Do these need to be included just to install the gem? Or are they
# required only for testing and/or the demo app (which has been submoduled
# anyway)
gem 'dragonfly', '~> 0.9'
gem 'paperclip'
gem "carrierwave", "~> 0.5.6"

# For minimal Carrierwave processing
# TODO - Is this necessary?
gem "mini_magick", "~> 3.3"

gem 'rack-cache', :require => 'rack/cache'
gem 'rails', '~> 3.0'

group :test do
  gem 'shoulda-context'
  gem 'mocha' # Make sure mocha is loaded at the end ...
end

group :development, :test do
  gem 'factory_girl'

  platforms :jruby do
    gem 'activerecord-jdbc-adapter', :require => false

    gem 'jdbc-mysql'
    gem 'jdbc-postgres'
    gem 'jdbc-sqlite3'

    gem 'jruby-openssl' # JRuby limited openssl loaded. http://jruby.org/openssl
  end

  platforms :ruby do
    gem 'mysql2', '0.2.7'
    gem 'pg'
    gem 'sqlite3'
  end
end

# MongoDB support is still in "beta" mode, so I'm not testing it for the moment.
group :production do
  gem 'mongoid'

  platforms :ruby do
    gem 'bson_ext'
  end
end

group :production do
  platforms :jruby do
    gem 'activerecord-jdbc-adapter'
    gem 'jdbc-sqlite3'
  end

  platforms :ruby do
    gem 'sqlite3'
  end
end
