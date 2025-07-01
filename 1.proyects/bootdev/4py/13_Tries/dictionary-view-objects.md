---
id: dictionary-view-objects
aliases: 
tags:
  - python
  - dictionaries
prev: "[[13.7_longest-common-prefix]]"
---

# dictionary-view-objects
The objects returned by `dict.keys()`, `dict.values()` and `dict.items()` are view objects.
They provide a dynamic view on the dictionary's entries, which means that when the dictionary changes, the view reflects these changes.

Dictionary views can be iterated over to yield their respective data, and support membership tests:

An example of a dictionary view usage:
```python
dishes = {'eggs': 2, 'sausage': 1, 'bacon': 1, 'spam': 500}
keys = dishes.keys()
values = dishes.values()

# iteration
n = 0
for val in values:
    n += val

print(n)
>>>504

# keys and values are iterated over in the same order (insertion order)
list(keys)
>>>['eggs', 'sausage', 'bacon', 'spam']
list(values)
>>>[2, 1, 1, 500]

# view objects are dynamic and reflect dict changes
del dishes['eggs']
del dishes['sausage']
list(keys)
>>>['bacon', 'spam']

# set operations
keys & {'eggs', 'bacon', 'salad'}
>>>{'bacon'}
keys ^ {'sausage', 'juice'} == {'juice', 'sausage', 'bacon', 'spam'}
>>>True
keys | ['juice', 'juice', 'juice'] == {'bacon', 'spam', 'juice'}
>>>True

# get back a read-only proxy for the original dictionary
values.mapping
>>>mappingproxy({'bacon': 1, 'spam': 500})
values.mapping['spam']
>>>500
```
