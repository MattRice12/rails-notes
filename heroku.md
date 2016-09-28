# brew install heroku

# Gemfile
  ruby '2.3.0'
  replace 'sglite3' with 'pg'

  group :production do
    gem 'rails_12factor'
  end

# database.yml
  adapter: postgresql
  databases: development_<app>
             test_<app>
             production_<app>

bundle

rake db:create db:migrate db:seed

# databasing
heroku create <app_name>
heroku run rake db:migrate db:seed

# git got
git add.
git commit -m "heroku"
git push heroku master
