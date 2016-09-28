#Gemfile
group :test do
  gem 'cucumber-rails', :require => false
  gem 'database_cleaner'

  gem 'capybara'
end

#bundle

#rails g cucumber:install

#features/support/
  require 'capybara/rails'

#atom plugins


#create feature --> user_authentication.features

Feature:As a User, In order to use the app, I would like to be able to login

  Scenario: Existing User Logs In
    Given I have an existing user account
    When I visit "/sign_in"
    And I fill in "Email" with "user@example.com"
    And I fill in "Password" with "password"
    And I press "Submit"
    Then I should see "Welcome user!"
    And I should see "Homepage"

  Scenario: User Without an Account Signs Up


#rake db:test:prepare
  ---> prepares the test database

#cucumber

#copy/paste the return in terminal

#Create a Step Definition File

#features/step_definition --> user_authentication_steps.rb
  paste what you copied


  Given(/^I have an existing user account$/) do
    User.create(email: "user@example.com", name: "user", password: "password")
  end

  When(/^I visit "([^"]*)"$/) do |path|
    visit(path)
  end

  ...*


*
asdfj


#Best Practices
  /features/step_definition/shared_steps
    cut and paste everything from user_authentication_steps.rb into here
    do this because it really includes nothing about authentication
