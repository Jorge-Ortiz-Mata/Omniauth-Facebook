# Omniauth Facebook Authentication.

Ruby on Rail app. Users can sign up using their google accounts.

## Sumarize.

In this project, you will find all the configuration in order
to allow users sign up using their own facebook accounts.
Besides, you will learn how to configure your app to deploy it
to heroku.

## Software.

* Ruby 3.0.1
* Rails 6.1.4.7
* Windows 10
* VS Code.
* PostreSQL.
* Heroku.

## Process.

All the steps you will find in the sections below.

### Step 1. Gemfile.

Add the next gems into your gemfile.rb

* gem 'devise'
* gem 'omniauth-facebook'
* gem 'omniauth'
* gem 'omniauth-rails_csrf_protection'
* gem 'omniauth-google-oauth2'
* gem 'pg' <- **Production group**
* gem 'sqlite' <- **Development group**

### Step 2. Adding devise user model and pages controller.

Type the next commands in the command prompt.

1. Generate pages controller: `rails g controller pages home`
2. Install devise: `rails g devise:install`
3. Paste and add notice and alert messages.
4. Generate User model: `rails g devise User`
5. Generate devise views: `rails g devise:views`
6. Run rails migrate: `rails db:migrate`
7. Add the links in order to navigate to the sign un and aign in pages.

### Step 3. Configure routes.

Add the nex code in your routes.rb

```
Rails.application.routes.draw do
  devise_for :users, controllers: { omniauth_callbacks: 'users/omniauth_callbacks' }
  root 'pages#home'
end
```

 ### Step 4. Add AddOmniauthToUsers migration.

1. Run a new migration by typing the next command: `rails g migration AddOmniauthToUsers provider:string uid:string`
2. Type the command: `rails db:migrate`

### Step 5. Create Facebook app.

1. Go to https://developers.facebook.com/ and sign in.
2. Go to my apps and create a new app.
3. Select the type of your app.
![](app/assets/images/image-1.PNG)
4. Add a name for your app and your email. After that, click on **Create app**
![](app/assets/images/image-2.PNG)

### Step 6. Configure Facebook app.

1. Go to basic configuration and add the next options.
![](app/assets/images/image-3.PNG)
![](app/assets/images/image-4.PNG)
![](app/assets/images/image-5.PNG)

