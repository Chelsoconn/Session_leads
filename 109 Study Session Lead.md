109 Study Session Lead



P (Problem)

E (Examples)

D (Data Structure)

A (Algorithm)

C (Code)



```ruby 
x = [1,2,3,4,5]



new_array = []



x.each_index do |ind1|

  x.each_index do |ind2|

​    new_array << x[ind1..ind2] if ind2 >= ind1

  end

end



p new_array #[[1], [1, 2], [1, 2, 3], [1, 2, 3, 4], [1, 2, 3, 4, 5], [2], [2, 3], [2, 3, 4], [2, 3, 4, 5], [3], [3, 4], [3, 4, 5], [4], [4, 5], [5]]



x.permutation.to_a

x.combination(2).to_a
```





ex/

https://www.codewars.com/kata/58af1bb7ac7e31b192000020/train/ruby

```ruby 
def find_summands n
  odd_array = []
  num = 1
  loop do 
    odd_array << num
    odd_array.shift if odd_array.length > n
    num += 2 
    break if odd_array.sum == n**3
  end
  odd_array
end


def find_summands(n)
  final_num = n**3
  arr = []
  start = (final_num/n) - n
  until arr.sum == final_num 
    arr << start 
    arr.shift if arr.length > n 
    start.odd? ? start += 2 : start += 1 
  end 
  arr 
end

def find_summands n
  (n*n-n+1..n*n+n).step(2).to_a
end

p find_summands(27)
```

