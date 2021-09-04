# _The Complete Ruby on Rails Developer Course_ Outline

## Overview

- Outline of [The Complete Ruby on Rails Developer Course](https://www.udemy.com/course/the-complete-ruby-on-rails-developer-course/) by Rob Percival and Mashrur Hossain. This is a work in progress. Not all lectures will be accounted for. (Current as of September 2021.)

## Content

### Section 2: The Ruby Programming Language

#### Introduction to Ruby

- [Official Ruby website](https://www.ruby-lang.org/en/)

- Basic "Hello World"

  ```ruby
  puts "Hello World"  # Prints "Hello World" (followed by newline) and returns `nil`.

  # Define a method.
  def say_hello
    p "Hello World"
  end

  say_hello  # Prints "Hello World" (followed by newline) and returns the string.

  # Define a method that accepts an argument.
  def say_something(str)
    print str
  end

  # Assign a string to a variable.
  greeting = "Hello World"

  say_something greeting  # Prints "Hello World" (without a newline) and returns `nil`.
  ```

- Run a Ruby file (any file with an `.rb` extension) by running `ruby <file_name>.rb`.

- Quickly access an interactive Ruby environment by running `irb` in your terminal.

#### Working with Strings

- Strings can be set with either single or double quotation marks: `'John'` or `"John"`.

- String interpolation is only possible when using double quotation marks:

  ```ruby
  first_name = 'John'
  last_name = 'Doe'

  "My name is #{first_name} #{last_name}."

  # => "My name is John Doe."
  ```

- Determine whether a value is a string (or any other class type) by using the `.class` method:

  ```ruby
  "John".class

  # => String
  ```

- View all available string methods: `"John".methods`

- Examples of string methods:

  ```ruby
  # Uppercase and reverse:
  "John".upcase.reverse

  # => "NHOJ"
  ```

  ```ruby
  # Substitute string characters:
  sentence = 'Welcome to the jungle.'
  sentence.sub('the jungle', 'utopia')

  # => "Welcome to utopia."
  ```

  ```ruby
  # Convert a string to an integer:
  input = '10'
  input.to_i

  # => 10
  ```

### Section 13: Rails installation and usage: Mac

#### Install RVM (Ruby version manager)

- Go to [Installing RVM](https://rvm.io/rvm/install) and follow the installation instructions.

#### Install Ruby

- Run `rvm list` to see what versions of Ruby have been installed on your system.

- Run `rvm list known` to see all versions of Ruby that are available for installation.

- Run `rvm install <version>` to install a specific version of Ruby (e.g., `rvm install ruby-3`).

- Run `rvm --default use <version>` to set a specific version to be the default interpreter (if more than one version is installed).

- Run `rvm use <version>` to switch to a specific version, and run `rvm use default` to switch back to the default version.

#### Install and use Ruby on Rails 6

- Install the following gems:

  - `gem install bundler`

  - `gem install webpacker` (makes it easy for your Rails application to work with Webpack)

- Run `gem install rails` to install the latest stable version of Rails. Alternatively, install a specific version (e.g., `gem install rails -v 6.1.4`).

- Run `gem list rails` to verify your installation of Rails.

- Run `rails new <app_name>` to create a new Rails application in the current directory.

- Run `rails s` from within your new application's root directory to start the Rails server (the Puma server).

#### Install and use Ruby on Rails 5

- **IMPORTANT:** You may need to use `rvm` to switch to an older version of Ruby (e.g., `ruby-2.6.6`) in order to run Rails 5.

- Install the latest version of Rails 5 by running `gem install rails -v 5.2.4.1`.

- Run `rails _5.2.4.1_ new <app_name>` to create a new Rails 5 application in your current directory (or just `rails new <app_name>` if only one version of Rails is installed on your current environment).
