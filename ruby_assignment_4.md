### 1. Given an array [1,2,3,2,5,6,9,6,5,3,2,2,1,8,10,10,7]. Create a hash and store the frequency of the array element.

```
arr = [1, 2, 3, 2, 5, 6, 9, 6, 5, 3, 2, 2, 1, 8, 10, 10, 7]
m = Hash.new(0)

arr.each do |i|
 m[i] += 1
end

puts m
```

### 2. Write a program to print sum of numbers from 100 to 200

```
sum=0
for i in 100..200
    sum+=i
end
puts sum
```

### 3. Write an exception for dividing by zero in Ruby.

```
class DivisionByZeroError < StandardError
  def initialize(message = "Division by zero is not allowed.")
    super(message)
  end
end

def divide_numbers(a, b)
  raise DivisionByZeroError.new("Cannot divide #{a} by zero.") if b == 0
  a.to_f / b.to_f
end

puts divide_numbers(6,9)
puts divide_numbers(3,0)
```

### 4. Write a program to find and replace all occurrences of a character in a string.

```
s="Captain America is the best Avenger."
s=s.gsub("A","V")
```
