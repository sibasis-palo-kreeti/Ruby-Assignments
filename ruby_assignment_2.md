### 1.Write a program to print first n odd numbers where n can be from 1 to 100

```
n=gets.chomp.to_i
for i in 1..100
  if i%2==1
    puts i
    n=n-1
  end
  break if n <= 0
end
```

### 2.Given an array of integers where elements can be from 1-7. every element maps to the day of the week. write a program to print it like

```
1-monday, 2-tuesday, 3-wednesday
  arr = [1, 5 , 7, 4, 2, 6, 1, 4, 2, 7];
  Output: 1-monday, 5-friday, 7-sunday ...
```

```
def solve(arr)

    dict = {
        1 => "monday",
        2 => "tuesday",
        3 => "wednesday",
        4 => "thursday",
        5 => "friday",
        6 => "saturday",
        7 => "sunday"
    }

    lists = arr.map { |day| "#{day}-#{dict[day]}"}.join(", ")
    return ans

end


arr = [1,5,7,4,2,6,1,4,2,7]

puts solve(arr)
```

### 3.Given an array of integers, sort the array using bubble, insertion or selection sort algorithm [any one] arr = [12, 15, 9, 4, 30, 3, 7];

```
arr = [12, 15, 9, 4, 30, 3, 7]

for i in 0...arr.length
    for j in 0...(arr.length-i-1)
      if(arr[j]>arr[j+1])
        temp=arr[j]
        arr[j]=arr[j+1]
        arr[j+1]=temp
      end
    end
end

puts arr
```
