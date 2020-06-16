# tracery-lists
## Lists for use in Tracery

[Kate Compton (@galaxykate)](http://www.galaxykate.com/) created [Tracery: a story-grammar generation library for javascript](https://github.com/galaxykate/tracery/tree/tracery2). In order to use it, you need lists of words.

Here are some of mine. I use them with [Allison Parrish](http://www.decontextualize.com/)'s [pytracery](https://github.com/aparrish/pytracery).

It goes more or less like this:

```python
import os
import tracery
from tracery.modifiers import base_english

# This assumes you only have .txt files in this path.
#
# And also that your base rules are contained in a file called 'origin.txt'
#   This will be the be-all, end-all of your creative engine
path = 'your/ad/could/be/here'

rules = {}
txtfiles = os.listdir(path)

for file in txtfiles:
    basename = file[:-4]  # remove the extension
    #print(basename)
    with open(path+file) as f:
            temp_list = f.read().splitlines()
            rules[basename] = temp_list

grammar = tracery.Grammar(rules)
grammar.add_modifiers(base_english)

for _ in range(5):
    print(grammar.flatten("#origin#"))
```
