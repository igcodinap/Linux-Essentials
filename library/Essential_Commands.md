# Essential Commands

### Logging into Linux
1. whoami
2. hostname
3. date
4. uname
5. passwd
6. touch
7. last
8. man
9. grep
10. find
11. xargs
12. time
13. file

### getting help with man
man shows command summary
- items in [brackets] are optional
- items in {a | b} must choose one
- ... means you may have more of the preceding item
- Use /pattern to search for some text and n for going to the next match
- Move in the man page with G and g
- man -k [pattern] displays all the man pages that have the pattern
- wc --> wordcount
- man man
- pinfo is another util for looking for information regarding some utilities
- /usr/share/doc contains additional help for some commands

Sections:
1. for end-user commands
8. for administrator, root commands
5. for configuration files

### Management Tools
1. ls
2. cp
3. cd
4. mkdir
5. rmdir / rm -r (better suitable)
6. mv

### globbing(wildcards)
* all matches
? one single char
[range] a range between two chars

### links
ln

#### hard links
creates another file pointing to the same inode registry
must be in the same partition
#### soft links (symbolic)
works like the commonly known shortcuts in windows
always use absolute paths, if not and you move it, it will become useless

### find
common options:
- find [f | d]
- size [+NM] where N is a number and M for megabytes
- exec [command] [command options] {} \;

### tar(tape archiver)
common options:
- compress: tar -cvf file /dir
- extract: tar -xvf my_archive -C [directory]
- show content: tar -tvf file.tar

### compression utilities
- gzip, the most common compression utility
1. gzip
2. gunzip
- bzip2, an alternative utility
- zip windows compatible syntax

### vi
- command mode
to go to im [i,o,a,etc]
- input mode
to go back to cm [esc]

- create a file
vi [filename]
commands
- i: insert mode
- d: delete
- o: new line
- p: paste
- v: make a block
- u: undo 
- gg: start of the document
- search: /[pattern]
- search and replace: %s/[pattern]/[newpattern]/g

### pager
- less: has almost the same command line uses than vi or man
- head: first lines
- tail: last lines

### readers
- cat
b: number of lines
A: show all non-printable chars
n: number of lines but not empty ones
s suppressed repeated empty lines

- tac: same as cat but in inverted order

### grep
filtering utility
looks for a pattern in a file
options
- v: all minus the pattern
- A#: see also 3 lines after
- B#: see also 3 lines before

* remember that any in single quotes is interpreted by the command and not the bash shell
* egrep get better the regexp

regexp
- . any char
- ^ lines that start with the following chars
- $ lines that end with the previous chars
- [] set of chars
- {#} #times the previous char or set of chars
- * zero or non of the pattern
- ? one or more of the pattern

### text processing utilities
- cut: older filter utility
- awk: pattern scanning 
- sort: for sorting
- tr: for translation
- sed: to replace chars in a file from command line