# _The Complete Ruby on Rails Developer Course_ Outline

## Overview

- Outline of [The Complete Ruby on Rails Developer Course](https://www.udemy.com/course/the-complete-ruby-on-rails-developer-course/) by Rob Percival and Mashrur Hossain. This is work in progress, and not all lectures will be accounted for. (Current as of September 2021.)

## Content

### Section 1: Introduction and Setup

### Section 13: Rails installation and usage: Mac

#### 414. Install RVM (Ruby version manager)

- Go to [Installing RVM](https://rvm.io/rvm/install) and follow the installation instructions.

#### 415. Install Ruby

- Run `rvm list` to see what versions of Ruby have been installed on your system.

- Run `rvm list known` to see all versions of Ruby that are available for installation.

- Run `rvm install <version>` to install a specific version of Ruby (e.g., `rvm install ruby-3`).

- Run `rvm --default use <version>` to set a specific version to be the default interpreter (if more than one version is installed).

- Run `rvm use <version>` to switch to a specific version, and run `rvm use default` to switch back to the default version.

#### 417. Install and use Ruby on Rails 6

- Install the following gems:

  - `gem install bundler`

  - `gem install webpacker` (makes it easy for your Rails application to work with Webpack)

- Run `gem install rails` to install the latest stable version of Rails. Alternatively, install a specific version (e.g., `gem install rails -v 6.1.4`).

- Run `gem list rails` to verify your installation of Rails.

- Run `rails new <app_name>` to create a new Rails application in the current directory.

- Run `rails s` from within your new application's root directory to start the Rails server (the Puma server).

#### 418. Install and use Ruby on Rails 5

- **IMPORTANT:** You may need to use `rvm` to switch to an older version of Ruby (e.g., `ruby-2.6.6`) in order to run Rails 5.

- Install the latest version of Rails 5 by running `gem install rails -v 5.2.4.1`.

- Run `rails _5.2.4.1_ new <app_name>` to create a new Rails 5 application in your current directory (or just `rails new <app_name>` if only one version of Rails is installed on your current environment).
