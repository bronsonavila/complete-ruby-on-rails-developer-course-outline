# _The Complete Ruby on Rails Developer Course_ Outline

## Overview

- Outline of [The Complete Ruby on Rails Developer Course](https://www.udemy.com/course/the-complete-ruby-on-rails-developer-course/) by Rob Percival and Mashrur Hossain. This personal quick reference guide is a work in progress. Not all lectures or concepts will be accounted for. (Current as of September 2021.)

## Content

### Section 2: The Ruby Programming Language

#### Introduction to Ruby

- Useful links:

  - [Official Ruby website](https://www.ruby-lang.org/en/)

  - [Try Ruby](https://try.ruby-lang.org/)

  - [RuboCop](https://github.com/rubocop/rubocop) is a linter and code formatter that enforces many of the guidelines outlined in the [Ruby Style Guide](https://rubystyle.guide/).

- Basic "Hello World":

  ```ruby
  puts "Hello World"  # Prints "Hello World" (followed by newline) and returns `nil`.

  # Define a method:
  def say_hello
    p "Hello World"
  end

  say_hello  # Prints "Hello World" (followed by newline) and returns the string.

  # Define a method that accepts an argument:
  def say_something(str)
    print str
  end

  # Assign a string to a variable:
  greeting = "Hello World"

  say_something greeting  # Prints "Hello World" (without a newline) and returns `nil`.
  ```

- Run a Ruby file (any file with an `.rb` extension) by running `ruby <file_name>.rb`.

- Quickly access an interactive Ruby environment by running `irb` in your terminal.

#### Strings

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

#### Numbers

- All numbers without decimals will operate as integers and will only yield integers as their calculated result. If a calculated result should contain a decimal, then at least one number in the calculation must be a float:

  ```ruby
  10 / 4

  # => 2

  10.0 / 4

  # => 2.5

  # Convert 4 to a float:
  10 / 4.to_f

  # => 2.5
  ```

- A string can be multiplied by a number to perform string concatenation:

  ```ruby
  '-' * 20

  # => "--------------------"
  ```

  - Alternative method: `20.times { print '-' }`

#### Comparison Operators

- Basic operators:

  ```ruby
  ==  # Equal to

  !=  # Not equal to

  >   # Greater than

  >=  # Greater than or equal to

  <   # Less than

  <=  # Less than or equal to
  ```

  - **NOTE:** Ruby supports the `===` operator, but it behaves as a [case subsumption operator](https://stackoverflow.com/a/4467823/9027907).

- To check if two values are equal both in value and type, use `.eql?`:

  ```ruby
  10.eql?(10.0)

  # => false

  10.eql?(10)

  # => true
  ```

#### Methods

- Ruby automatically returns the last evaluated expression within a method, so no `return` keyword is necessary:

  ```ruby
  def multiply(a, b)
    a * b
  end

  multiply(2, 3)

  # => 6
  ```

  - **NOTE:** It is also valid to omit the parentheses when calling a function:

    ```ruby
    multiply 2, 3

    # => 6
    ```

#### Branching (Conditionals)

- Example:

  ```ruby
  if foo && bar
    puts 'Both foo and bar are true.'
  elsif foo || !bar
    puts 'Either foo is true, or bar is false.'
  else
    puts '🙃'
  end
  ```

- `if` statements can also be evaluated on a single line:

  ```ruby
  puts 'foo is true' if foo == true
  ```

#### Arrays and Iterators

- Basic array methods:

  ```ruby
  arr = [1, 2, 3, 4]

  arr.last

  # => 4

  arr.shuffle

  # => [2, 3, 1, 4]

  # Original array has not been mutated.
  arr

  # => [1, 2, 3, 4]

  arr.shuffle!

  # => [4, 3, 1, 2]

  # The original array has been mutated due to adding `!` after `.shuffle`:
  arr

  # => [4, 3, 1, 2]

  arr.unshift(0)

  # => [0, 4, 3, 1, 2]

  arr.append(5)
  arr << 6

  # => [0, 4, 3, 1, 2, 5, 6]

  arr.empty?

  # => false

  arr.include?(7)

  # => false
  ```

  - Ruby arrays also include other standard programming methods; e.g.: `.push`, `.pop`, `.join`, `.split`.

- A range can be converted to an array:

  ```ruby
  (1..4).to_a

  # => [1, 2, 3, 4]
  ```

- Create an array of strings:

  ```ruby
  %w(foo bar baz)

  # => ["foo", "bar", "baz"]

  _

  # => ["foo", "bar", "baz"]
  ```

  - **TIP:** The last used value is automatically assigned to the `_` (underscore) variable, which can be accessed at any time.

- Iterate over an array by using the `.each` method:

  ```ruby
  arr = [1, 2, 3, 4]

  arr.each do |i|
    print i
  end

  # Alternative syntax for single-line statements:
  arr.each { |i| print i }
  ```

  - This method of iteration is generally preferred over a `for` loop:

    ```ruby
    arr = [1, 2, 3, 4]

    for i in arr
      print i
    end
    ```

  - **NOTE:** See [Loops (for, while, do..while, until)](https://www.geeksforgeeks.org/ruby-loops-for-while-do-while-until/) for more information on Ruby loops.

- Filter an array with the `.select` method:

  ```ruby
  arr = [1, 2, 3, 4]

  # Select only the odd numbers in the array:
  arr.select { |i| i.odd? }

  # => [1, 3]
  ```

#### Hashes

- Example:

  ```ruby
  hash = { 'a' => 1, 'b' => 2, 'c' => 3 }

  hash['a']

  # => 1
  ```

- Hash keys can also be symbols instead of strings:

  ```ruby
  hash = { a: 1, b: 2, c: 3 }

  hash[:b]

  # => 2

  hash[:c] = 4
  hash[:d] = 8
  hash

  # => { :a => 1, :b => 2, :c => 4, :d => 8 }
  ```

- Use `.keys` and `.values` methods to get an array of a hash's keys/values respectively:

  ```ruby
  hash = { a: 1, b: 2, c: 3 }

  hash.keys

  # => [:a, :b, :c]

  hash.values

  # => [1, 2, 3]
  ```

- Iterate over a hash:

  ```ruby
  hash = { a: 1, b: 'foo', c: 3 }

  hash.each { |key, value| puts "#{key} / #{value}" }

  # a / 1
  # b / foo
  # c / 3

  hash.select { |key, value| value.is_a?(Integer) }

  # => { :a => 1, :c => 3 }

  hash.each { |key, value| hash.delete(key) if value.is_a?(Integer) }

  # => { :b => "foo" }
  ```

#### Classes

- Example:

  ```ruby
  class User
    attr_accessor :name, :email   # Read/write access
    attr_reader :_id               # Read access only

    def initialize(name, email)
      @_id = rand()
      @name = name
      @email = email
    end

    def get_info
      {
        name: @name,
        email: @email
      }
    end

    # This string is displayed whenever printing an instance.
    def to_s
      "User: #{@name}.\nEmail: #{@email}."
    end

    # Use `self` to define Class-only methods.
    def self.attrs
      [:name, :email]
    end
  end

  user = User.new('John', 'john@foo.com')

  user.get_info

  # => { :name => "John", :email => "john@foo.com" }

  user.email = 'john@bar.com'

  puts user

  # User: John.
  # Email: john@bar.com.
  ```

  - **NOTE:** If the `attr_accessor` is not provided, then attributes can only be read and modified via getters and setters:

    ```ruby
    class User
      def initialize(name)
        @_id = rand()
        @name = name
      end

      # Getter
      def name
        @name
      end

      # Setter
      def name=(name)
        @name = name
      end
    end

    user = User.new('John')

    user.name = 'John Doe'
    user.name

    # => "John Doe"

    user._id = 'baz'

    # => NoMethodError (undefined method `_id=' for #<User @name="John", ...
    ```

### Section 13: Rails Installation and Usage (Mac)

#### Install RVM (Ruby Version Manager)

- Go to [Installing RVM](https://rvm.io/rvm/install) and follow the installation instructions.

#### Install Ruby

- Run `rvm list` to see what versions of Ruby have been installed on your system.

- Run `rvm list known` to see all versions of Ruby that are available for installation.

- Run `rvm install <version>` to install a specific version of Ruby (e.g., `rvm install ruby-3`).

- Run `rvm --default use <version>` to set a specific version to be the default interpreter (if more than one version is installed).

- Run `rvm use <version>` to switch to a specific version, and run `rvm use default` to switch back to the default version.

#### Install and Use Ruby on Rails 6

- Install the following gems:

  - `gem install bundler`

  - `gem install webpacker` (makes it easy for your Rails application to work with Webpack)

- Run `gem install rails` to install the latest stable version of Rails. Alternatively, install a specific version (e.g., `gem install rails -v 6.1.4`).

- Run `gem list rails` to verify your installation of Rails.

- Run `rails new <app_name>` to create a new Rails application in the current directory.

- Run `rails s` from within your new application's root directory to start the Rails server (the Puma server).

#### Install and Use Ruby on Rails 5

- **IMPORTANT:** You may need to use `rvm` to switch to an older version of Ruby (e.g., `ruby-2.6.6`) in order to run Rails 5.

- Install the latest version of Rails 5 by running `gem install rails -v 5.2.4.1`.

- Run `rails _5.2.4.1_ new <app_name>` to create a new Rails 5 application in your current directory (or just `rails new <app_name>` if only one version of Rails is installed on your current environment).
