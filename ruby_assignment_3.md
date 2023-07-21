### 1.Explain implicit blocks with an example.

In Ruby, blocks can be either implicit or explicit.

Implicit blocks are anonymous blocks that are passed to a method as a parameter. They are denoted by a dot . followed by a block of code.

Implicit blocks are not accessible outside of the method that they are passed to.

For example:

```
def my_method(&block)
  block.call
end

my_method do
  puts "This is an implicit block"
end
```

### 2.Write a code where a proc is passed as an argument to the method.

```
def func(&x)
    x.call
end

block=Proc.new{puts "this is a proc which is passsed as argument to func method"}

func(&block)
```

### 3.Differentiate between blocks, procs, and lambdas.

Blocks are anonymous blocks of code that are passed to methods as parameters. They are denoted by a dot . followed by a block of code. For example:

```
def my_method(&block)
  block.call
end

my_method do
  puts "This is a block"
end
```

Procs are objects that represent blocks of code. They can be created using the Proc.new method. For example:

```
proc = Proc.new { puts "This is a proc" }
proc.call
```

Lambdas are a type of proc that enforces arity and returns from the lambda itself. They are created using the lambda keyword. For example:

```
lambda = lambda { puts "This is a lambda" }
lambda.call
```

**4.WAP to check if a string is palindrome.**

```
def isPalindrome(s)
    for i in 0...(s.length/2)
        if s[i]!=s[s.length-1-i]
            puts "String is not a Palindrome!"
            return
        end
    end
    puts "String is Palindrome!"
    return
end
```

**5.WAP to print the sum of maximum and minimum element in an array**

```
arr = [95, 66, 78, 13, 26, 78]
puts arr.min+arr.max
```
