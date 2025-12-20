# General

# Lesson/Exercises ideas
## Greet plugin
Simple plugin that greets the player with some text like "Welcome \<name\>"

Concepts learned:
- Strings
- Write to screen / chat
- String operation +
- Formatted strings


## Bookmark plugin
The user can type in chat one of 3 commands:
- bookmark add \<name\>
- bookmark list
- bookmark go \<name\>

**bookmark add** adds the current player position to the list under the given name.\
**bookmark list** prints the list of saved bookamrks.\
**bookmark go** teleports the player to the location saved under the given name.

Concepts learned:
- Read from input (from chat).
- Write to chat?
- Static variables or classes.
- HashMap

# Misc
Beofre commiting md can be tested with pandoc:
```
pandoc -s -f gfm -t html todo.md -o todo.html
```
