# tracery-lists

## Lists for use in Tracery

[Kate Compton (@galaxykate)](http://www.galaxykate.com/) created [Tracery: a story-grammar generation library for javascript](https://github.com/galaxykate/tracery/tree/tracery2). In order to use it, you need lists of words.

Here are some of mine. I use them with [Allison Parrish](http://www.decontextualize.com/)'s [pytracery](https://github.com/aparrish/pytracery). **Please let me know if you use these**, makes me happy to know this work can help others.

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

**Don't forget to read some documentation at the wiki!**

## A note on fictional characters

1. The lists of fictional characters come exclusively from Public Domain sources. I don't know how copyright law applies to projects like this, storing and using copyright-protected characters for pseudo-random text creation. As such, they won't be admitted.
2. The first contributor (@andycyca) is well aware that women are under-represented in lists like these, in no small part because of centuries of biases in society at large and, in consequence, literature. **I'm trying to add as many female characters as possible** and would appreciate comments and suggestions to improve this list.
3. The above point also applies to other groups that have been marginalized and/or discriminated against throughout history; including (but not limited to) LGBTQ persons, native peoples, people of African descent and countless others. **If anyone knows a better way of representing these groups, please let me know.**
4. It's also worth noting that **Public Domain characters can be re/written as having different sex, gender, nationality, background**. Reimagining the Public Domain is another way of appropriating it. If anyone decides to do this, please [don't just change the descriptions of a character's physical aspect and call it 'diverse'](https://www.npr.org/2020/02/06/803473296/author-l-l-mckinney-barnes-noble-diverse-editions-are-literary-blackface)

## See also:

- [dariusk/corpora](https://github.com/dariusk/corpora) for a different, deeper approach to generating things