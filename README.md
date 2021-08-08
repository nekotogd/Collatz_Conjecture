# Collatz_Conjecture
Jupyter Notebook on how to graph the Collatz Conjecture.

https://gesis.mybinder.org/binder/v2/gist/nekotogd/954eeed7fa9846bd6991d347a4e09336/ca9bc3f2a7462e6aa43d6e4444abef657e9afa10

# Why I made this

I actually wanted to learn how to create and use Jupyter Notebooks.

It seems like such a cool syste mthat I really wanna learn how to mockup things in.

It sort of gives you an interactive way on looking back at things that you tried through your own notes and can also help document your code in a much neater and descriptive manner using the power of Markdown!

# Just the code

For anyone who just wanted a way to graph the Collatz Conjecture in Python, here's the code:

![image](https://user-images.githubusercontent.com/81257780/128608506-75f5df3b-7f04-4b04-af6a-32cb69e6e69b.png)

To Copy:

```python
import matplotlib.pyplot as plt

start_number = input("Input a starting number: ")

if start_number.isnumeric():
    start_number = int(start_number)
else:
    quit()

MAX_ITERATIONS = 200

new_number = start_number
repeat_pattern = [4, 2, 1]
test_pattern = []
plt.plot(0, start_number)
for i in range(MAX_ITERATIONS):
    prev_number = new_number
    if new_number % 2 == 0:
        new_number /= 2
    else:
        new_number = (3 * new_number) + 1
    
    if new_number in repeat_pattern:
        test_pattern.append(new_number)
    if len(test_pattern) >= 3:
        if test_pattern == repeat_pattern:
            break
        else:
            test_pattern.clear()
    
    plt.plot((i-1, i), (prev_number, new_number))

plt.show()
```
