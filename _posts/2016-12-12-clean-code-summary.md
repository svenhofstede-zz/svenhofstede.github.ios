---
title: What Clean Code taught me
published: true
tags:
- Personal
---

I'm currently working on reading through Clean Code by Robert C. Martin. It was clear from the start that the book is full of incredible content and it's well worth the time to study it properly. I'm trying to capture the key take-aways I have come across. There is much more to the book then what I'm highlighting here but these are things that were somewhat new to me and stuck in my mind as being worth remembering. I would suggest any programmer to have a look at this book in full. 

I'm approaching this book from an un-experienced programming in terms of application development. Most of the concepts/patterns are new to me.

This blog post is work-in-progress while working myself through the book. It will loosely follow the structure of the book. 

## The Art of Naming

*There are two hard things in computer science: cache invalidation, **naming things**.*

The naming of variables and functions is an art in itself. You need to come up with a name that perfectly explains why and how a variable or function is used and what it is. It can't be too long but it shouldn't be too short. Longer is better then shorter is that means the intent is clear. 

#### Make it Searchable

If possible, make sure the name is searchable. You need to be able to easily jump to a variables. Don't call them `x`, `counter` or `max_number`. If you are using `counter` once, you'll probably use it often so searching the right one is inconvenient. And you don't want the search to bring you to every `x` in the text. 

#### Talking about variables

Make stuff pronounceable. This helps greatly in talking about the functions and variables with other people. Instead of having to refer to `df_incr` we can just **say** `dataframe_incremental`. Yes it might be longer to type but copy-paste and auto-complete are commonplace.

#### Stick to a word per concept

Agree and stick to a single word for a single concept. Are you *fetching* or are you *getting* a record? Decide and use this going forward when necessary. Don't mix `get_record_by_id` with `fetch_records`.

## Functions

#### Reduce complexity

Functions should do one thing. 

For readability you want to limit the number of indent levels to 1 or 2. Anything more then 2 probably means your function is doing *too much*. Functions should have **at most** 3 arguments but ideally you should be aiming for zero if at all possible. Increasing the number of arguments will:

* Hard to understand what the function does. 
* They pollute the simplicity of the API
* It makes testing more complex 
 
If you notice your functions really needs multiple argument, consider if it makes sense to replace them by an input object instead.

#### Avoid side effects

> In computer science, a function or expression is said to have a side effect if it modifies some state or has an observable interaction with calling functions or the outside world.

Side-effects are lies. Your function is doing something that isn't advertised in the name. They also make it difficult to test your function as you need to set-up the *outside world* for your function to work. Pure functions are much more reliable as they are guaranteed to return the same value for a given input.  

#### Extract try-catch blocks. 

By writing your code in a try block you are mixing error processing with the actual processing.


```python
try:
  i = 1
  i = do_something_to_variable(i)

  do_something()
  do_another_thing()
except:
  raise
```  

Instead pull this out into a seperate function.

```python
def do_loads_of_things():
  i = 1
  i = do_something_to_variable(i)

  do_something()
  do_another_thing()

try:
  do_loads_of_things()
except:
  raise
```

#### Write test, write code, refactor

It's hard to write clean functions on first pass and people rarely do. There is nothing wrong with writing ugly code that just works and then refactoring it to make it clean.

## Comments

Comments, in general, should be avoided. Try to replace with more expressive function names. 

Don't leave commented code hanging around. If you don't need it, get rid of it.  If someone (or even yourself) comes along at a later date they don't know why the code is commented out. They would fear either removing or uncommenting it. Remember you have source control to retrieve old code. Same thing for journal comments, this is dealt with by the source control. No need to track this in the code.

Add comments near the source of the thing you are commenting. Don't add a comment for a function where you are using the function. Instead comment where the function is defined.

## Formatting 

*To be continued*

## Objects and Data Structures

*To be continued*

## Error Handling

*To be continued*

## Boundaries

*To be continued*

## Unit Tests

*To be continued*

## Classes

*To be continued*

## Systems

*To be continued*

## Emergence

*To be continued*

## Concurrency

*To be continued*

## Successive Refinement

*To be continued*

