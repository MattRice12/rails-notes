https://gist.github.com/thebucknerlife/10090014

##Gemfile
gem 'bcrypt', '~> 3.1.7'
bundle install

##Routes
  Rails.application.routes.draw do
    get '/login' => 'sessions#new'
    post '/login' => 'sessions#create'
    get 'logout' => 'sessions#destroy'

    get '/signup' => 'users#new'

    post 'sessions/authenticate'
  end

##Create a Users Controller
class UsersController < ApplicationController
  def new
    render locals: {
      user: User.new
    }
  end

  def create
    user = User.new(user_params)
    if user.save
      session[:user_id] = user.id
      redirect_to root_path, notice: 'Successfully created an account and signed in!'
    else
      flash[:alert] = "User could not be created due to errors."
      render template: 'users/new.html.erb', locals: {
        user: user
      }
    end
  end

  private

  def user_params
    params.require(:user).permit(:name, :email, :password, :password_confirmation)
  end
end

#Model
  class User < ActiveRecord::Base
    has_secure_password
  end

##Views --
#users/new.html.erb
  <%= render 'form', user: user, form_title: "Create New User" %>

#users/\_form.html.erb
  <h1>Signup!</h1>

  <%= form_for(user) do |f| %>

    Username: <%= f.text_field :username %>
    Password: <%= f.password_field :password %>
    Password Confirmation: <%= f.password_field :password_confirmation %>

      <%= f.submit "Submit", class: "btn" %>

    <div class="back btn">
      <%= link_to "back", root_path %>
    </div>
  <% end %>

##
