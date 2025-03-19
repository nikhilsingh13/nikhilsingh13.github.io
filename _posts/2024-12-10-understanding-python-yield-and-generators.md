---
layout: single
title:  "Understanding Python's 'yield' and Generators"
date:   2024-12-10 15:00:00 +0100
categories: python generators
header:
  overlay_image: '/img/python-yield.png'
  show_overlay_excerpt: false
use_math: true
author_profile: false
toc: true
toc_label: "Contents"
toc_icon: "list"
---

# Python's 'yield' simplified: Deep Dive into Generators

-----------------------------

## Introduction
Generators are quite an interesting feature in Python. It allows developers to manage memory efficiently and handle large data streams with ease _(shown as a real life usecase)_. 

In this blog post, I'll show the `yield` keyword usage, which lies at the heart of creating generators. 

Examples include basic usage to real-life applications which can be used directly into your python projects.

## Basic Generators: The Fundamentals
Generators are functions that allow you to declare a function that behaves like an iterator. They simplify code and make memory management easier. 

Function paused ↩️ ← `yield` value → Function resumes 🔄

> `next()` is the typical way to iterate over a generator object.

Let's start by understanding the basic syntax and functionality of a generator.

## `Hello World` Generator: A Simple Example
To illustrate the simplicity and power of generators, here's a straightforward example that yields a couple of friendly greetings:
```python
def fun_generator():
    yield "Hello world!!"
    yield "Bbye...!"
```

## Infinite Sequences: Beyond Finite Limits
One practical use-case of generators is in creating infinite sequences. These can be particularly useful in 
1. simulations
2. iterative calculations
3. Endless sequence number   

etc.

```python
def inf_sequence():
    num = 0
    while True:
        yield num
        num += 1
```

In practical scenarios, you'll find the usage of infinite sequnces when data is generated continouously. For example: 

1. **Sensor data processing**: In IoT applications, sensors can be programmed in such a way that monitoring is required continuously. In such scenarios, because of memory limitations, it is beneficial to process the data as it comes.

2. **Financial data processing**: In financial markets, trading algorithms often need to handle streaming tick data that comes in continuously throughout trading hours.

3. **Game Development**: In game development, procedural content generation, like landscapes or levels, can be generated on the fly as the player progresses. This keeps the memory usage low and the game responsive.

There can be many more....

## Generator Expressions: Inline Generators
For simpler scenarios, Python offers the compact syntax of generator expressions. These are similar to list comprehensions but for generators:

```python
gen = (x**2 for x in range(10))
```

**In what scenarios will one choose generator-expressions over list-comprehension?**

1. Generators are more memory-efficient than list comprehensions because they yield items one at a time and do not store the entire list in memory.

2. **LazyEval**: Generator expressions are lazy, meaning they generate values only as needed. So, it can lead to performance gains, especially in scenarios where the full result set is not a necessity, early stopping based on a condition or integrating with other lazy processing.

3. **Large Data Sets**: When working with large datasets that could potentially fill up your RAM, using a generator expression can avoid memory errors and slow performance issues.

## Real-Life Use Case: Streaming Large Datasets
When working with large datasets that don't fit into memory, generators can be a lifesaver. 

Here's how you can use `yield` to process large datasets efficiently:

```python
def data_streamer(file_path, batch_size=10):
    with open(file_path, 'r') as file:
        batch = []
        for line in file:
            batch.append(process_line(line))
            if len(batch) == batch_size:
                yield batch
                batch = []
        if batch:
            yield batch
```

## Conclusion
Generators and the `yield` keyword are powerful tools in Python's arsenal, providing an efficient way to handle data streams and iterative processes. 

Experiment with these examples and explore how you can integrate generators into your Python projects for better performance and scalability.

Have questions or insights about using `yield`? <a href="https://nikhilsingh.io/contact" target="_blank">Let me know</a>

[![Notebook](https://mybinder.org/badge_logo.svg)](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/yield_fn_work/blogpost_code.ipynb)


## References
For further exploration, here are some great links to check:
1. <a href="https://realpython.com/introduction-to-python-generators/#understanding-the-python-yield-statement" target="_blank">RealPython: Understanding yield</a>
2. <a href="https://www.geeksforgeeks.org/python-yield-keyword/" target="_blank">G4G: Python yield keyword</a>
3. <a href="https://www.datacamp.com/tutorial/yield-python-keyword" target="_blank">Datacamp: yield</a>
4. <a href="https://docs.python.org/3/reference/expressions.html#yield-expressions" target="_blank">Python doc</a>