### 1. Write ruby regex to accept basic email addresses, that contain a letter (any case) as its 1st character, followed by any number of word characters, then an ‘@’ symbol, again followed by any number of word characters, then a '.’ and finally a maximum of 4 letter (minimum 1).

```

regex = /^[a-zA-Z](\w*)@(\w*)\.[a-zA-Z]{1,4}$/
def check_mail_add(s, regex)
  if s =~ regex
    puts "Valid Mail ID"
  else
    puts "Invalid Mail ID"
  end
end
```

### 2. Let’s consider a ruby class Vehicle with following definition:

```
class Vehicle
 def initialize
    puts “I am a vehicle”
  end

  def max_speed
    puts “10”
  end
end
```

#### a. Define 2 classes Car and Rickshaw which inherit the class Vehicle.

#### b. Override method max_speed in both classes to output 100 and 25 for classes Car and Rickshaw respectively.

```
class Car < Vehicle
  def initialize()
    super()
  end
  def max_speed
    puts "100"
  end
end

class RickShaw < Vehicle
  def initialize()
  super()
  end
  def max_speed
  puts "25"
  end
end
```

### 3. Differentiate between Module and Mixins

In Ruby, modules and mixins are two related but distinct concepts. They are both used to add functionality to classes, but they serve different purposes and are used in different ways.

Module:

A module in Ruby is a container for a set of methods, constants, and other module-level elements. It cannot be instantiated or subclassed like classes. Its primary purpose is to provide a way to organize and reuse code in a modular and namespace-like manner.

Modules are commonly used to encapsulate related methods that can be included in multiple classes. They act as a collection of behavior that can be "mixed in" or "included" into classes.

You can use the include keyword to add a module's methods to a class. When a class includes a module, it inherits the module's methods as instance methods of the class.

It cannot satisfy multiple inheritance.

```
module Greetings
  def say_hello
    puts "Hello!"
  end
end

class MyClass
  include Greetings
end

obj = MyClass.new
obj.say_hello   # Output: "Hello!"
```

Mixins:

Mixins are a way of achieving multiple inheritance in Ruby, where a class can inherit functionality from multiple sources (superclasses) by "mixing in" one or more modules into the class.

By including a module in a class, the class gains all the methods defined in that module, effectively extending its functionality without the need for traditional subclassing.

Mixins allow you to share behavior across different classes without creating a hierarchy of subclasses, promoting code reusability and modularity.

It allows multiple inheritance in Ruby.

Example of mixins:

```
module Bird
  def have_beak()
  puts "I have a beak"
  end
end
module Fish
  def can_swim()
  puts "I can swim"
  end
end
class Duck
  def initialize()
    puts "I am a duck"
  end
include Bird
include Fish
end

donald=Duck.new()
donald.have_beak()
donald.can_swim()
```

output:

```
I am a duck
I have a beak
I can swim
```

In summary, modules are used for organizing and encapsulating code, while mixins are a way to add behavior to classes without full inheritance. Modules can be used independently, but when included in classes, they become mixins and contribute their behavior to the classes that include them.

### 4. Differentiate between Private and Protected methods

In Ruby, both private and protected methods are used to control the visibility and accessibility of methods within a class. However, there are some key differences between them, particularly in terms of who can access these methods and when they can be invoked:

Private Methods:
Private methods in Ruby can only be called from within the same class. They cannot be accessed by instances of the class or any other classes, even subclasses.
Private methods are used to encapsulate internal implementation details and to prevent external interference. They are typically used for helper methods or internal calculations that should not be exposed to the outside world.
To define a private method in Ruby, you use the private keyword followed by the method definitions.
Example:

```
class MyClass
  def public_method
    puts "This is a public method."
    private_method   # Private method can be called within the class
  end

  private

  def private_method
    puts "This is a private method."
  end
end

obj = MyClass.new
obj.public_method   # Output: "This is a public method." "This is a private method."
obj.private_method  # NoMethodError: private method `private_method' called for #<MyClass:0x00007f922812dfb8> (main.rb:13:in `<main>')
```

Protected Methods:
Protected methods in Ruby can be called from within the same class and its subclasses. They are accessible only to objects of the same class and its subclasses.
Protected methods are typically used when you want to allow certain methods to access information or behavior from other objects of the same class or its subclasses, while still preventing external access.
To define a protected method in Ruby, you use the protected keyword followed by the method definitions.
Example:

```
class MyClass
  def public_method
    puts "This is a public method."
    protected_method   # Protected method can be called within the class
  end

  protected

  def protected_method
    puts "This is a protected method."
  end
end

class MySubclass < MyClass
  def call_protected_method
    protected_method   # Protected method can be called from a subclass
  end
end

obj = MyClass.new
obj.public_method   # Output: "This is a public method." "This is a protected method."

sub_obj = MySubclass.new
sub_obj.call_protected_method   # Output: "This is a protected method."
```

In summary, private methods can only be called from within the same class, while protected methods can be called from within the same class and its subclasses. They both serve the purpose of controlling the visibility of methods and enforcing encapsulation, allowing for better control over class behavior and data hiding.
