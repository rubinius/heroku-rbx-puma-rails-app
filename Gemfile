source "http://rubygems.org"

ruby "1.9.3", :engine => "rbx", :engine_version => "2.0.0dev"

gem "rails", "~> 3.2.12"

group :production do
  gem "pg"
  gem "puma", "~> 2.0.0.b6"
end



# not a part of the heroku/rbx/puma demo
# just here to quiet the other noise
group :development do
  # gem "sqlite3-ruby", :require => "sqlite3"
  gem "sqlite3"
end

group :assets do
  gem "uglifier"
end
