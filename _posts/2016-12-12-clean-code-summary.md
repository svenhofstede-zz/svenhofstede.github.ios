---
title: What Clean Code taught me
published: true
tags:
- Personal
---

I'm currently working on reading through Clean Code by Robert C. Martin. It was clear from the start that the book is full of incredible content and it's well worth the time to study it properly. I'm trying to capture the key take-aways I have come across. There is much more to the book then what I'm highlighting here but these are things that were somewhat new to me and stuck in my mind as being worth remembering. I would suggest any programmer to have a look at this book in full. 

I'm approaching this book from an un-experienced programming in terms of application development. Most of the concepts/patterns are new to me.

This blog post is work-in-progress while working myself through the book. It will loosely follow the structure of the book. 

### The Art of Naming

*There are two hard things in computer science: cache invalidation, **naming things**.*

The naming of variables and functions is an art in itself. You need to come up with a name that perfectly explains why and how a variable or function is used and what it is. It can't be too long but it shouldn't be too short. Longer is better then shorter is that means the intent is clear. 

##### Make it Searchable

If possible, make sure the name is searchable. You need to be able to easily jump to a variables. Don't call them `x`, `counter` or `max_number`. If you are using `counter` once, you'll probably use it often so searching the right one is inconvenient. And you don't want the search to bring you to every `x` in the text. 

##### Talking about variables

Make stuff pronounceable. This helps greatly in talking about the functions and variables with other people. Instead of having to refer to `df_incr` we can just **say** `dataframe_incremental`. Yes it might be longer to type but copy-paste and auto-complete are commonplace.

##### Stick to a word per concept

Agree and stick to a single word for a single concept. Are you *fetching* or are you *getting* a record? Decide and use this going forward when necessary. Don't mix `get_record_by_id` with `fetch_records`.

### Functions

*To be continued*

### Comments

*To be continued*

### Formatting 

*To be continued*

### Objects and Data Structures

*To be continued*

### Error Handling

*To be continued*

### Boundaries

*To be continued*

### Unit Tests

*To be continued*

### Classes

*To be continued*

### Systems

*To be continued*

### Emergence

*To be continued*

### Concurrency

*To be continued*

### Successive Refinement

*To be continued*


