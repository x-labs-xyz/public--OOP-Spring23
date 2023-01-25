# 14. Memory Addresses: `&`

If you are ever curios about where exactly a value is stored on memory, you can use the symbol `&` to reveal it. 

```c++
string dessert = "cake";  
cout << &dessert << "\n"; 
// Output: 0x7ffe8c00f3f8

// updating value
dessert = "ice cream"; 
cout << &dessert << "\n";
// Output: 0x7ffe8c00f3f8
```

In this example, my variable `dessert` points to a memory location encoded as a hexadecimal value __0x7ffe8c00f3f8__ (your value will be different if you run the above example). Even if I update the value of the variable `dessert`, the memory address remains the same. That is, a particular address has been allocated to store the value of variable `dessert`. This [magic](https://cs.stanford.edu/people/eroberts/courses/cs106b/handouts/21-MemoryAndC++.pdf) of memory allocation and hexadecimal memory addressing is performed behind-the-scenes with machine-level logic.

## A visual example
Here is another example of how variables and memory addresses are mapped together. Let us assume we have initialized the following variables:

```c++
myvar = 25;
foo = &myvar;
bar = myvar;
```

Now let us see how they would map to each other in memory using the figure below.

![reference](mem-ref.png)

You can see that the variable `myvar` holds the value 25. `foo` stores the address (1776) as a _value_, while `bar` stores the same value as `myvar`.
