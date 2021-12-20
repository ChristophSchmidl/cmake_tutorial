# Module 4

- ```message()``` command
- Quoted and unquoted arguments
- Setting a variable
- Lists
- Strings

## Commands

- ```message(<mode-of-display> "the message")```
- ```set(<variable_name> <variable_value>)``` (all variables are type string)
- Dereferencing variables: ```${variable_name}```
- ```list()```
- ```string()```

Modes of Message Display

- ```message("Hello World)```
- ```message(STATUS "Hello World")```
- ```message(DEBUG "Hello World")```
- ```message(WARNING "Hello World")```
- ```message(FATAL ERROR "Hello World")```

Executing cmake in script mode

- ```cmake -P <script_name>```

Strings&Lists

- ```set(Name "Bob Smith")``` -> ```String 'Name' = Bob Smith```
- ```set(Name Bob Smith)``` -> ```List 'Name' = Bob;Smith```

list() command:

- ```list(<sub_command> <name_of_list> ... ... <return_variable>)```
- Subcommands: ```APPEND, REMOVE_ITEM, REMOVE_AT, REVERSE, REMOVE_DUPLICATES, INSERT, FILTER, GET, JOIN, SORT, LENGTH, SUBLIST, FIND```

string() command:

- Subcommands: ```FIND, REPLACE, PREPEND, APPEND, TOLOWER, TOUPPER, COMPARE```

file() command:

- Subcommands: ```READ, WRITE, RENAME, REMOVE, COPY, DOWNLOAD, LOCK```


## Notes

A string is also a list in CMake; with just one item.
