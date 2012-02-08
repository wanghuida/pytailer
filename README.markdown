# pytailer

A python implementation of GNU tail and head - forked from google code rev#3

http://code.google.com/p/pytailer/

## the original introduction

Python tail is a simple implementation of GNU tail and head.

It provides 3 main functions that can be performed on any file-like object that supports seek() and tell().

+ tail - read lines from the end of a file
+ head - read lines from the top of a file
+ follow - read lines as a file grows

It also comes with pytail, a command line version offering the same functionality as GNU tail. This can be particularly useful on Windows systems that have no tail equivalent.

to install

```bash
easy_install tailer
```

### examples

```python
f = open('test.txt', 'w')
for i in range(11):
    f.write('Line %d\n' % (i + 1))
    f.close()

    import tailer

# Get the last 3 lines of the file
tailer.tail(open('test.txt'), 3)
# ['Line 9', 'Line 10', 'Line 11']

# Get the first 3 lines of the file
tailer.head(open('test.txt'), 3)
# ['Line 1', 'Line 2', 'Line 3']

# Follow the file as it grows
for line in tailer.follow(open('test.txt')):
    print line
```
