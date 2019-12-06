# Bertelsmann Challenge Cloud 2019 

*Study Group : sg_cloudops*
*Edited By : Lesliel (6 Dec 2019)*


## Bash Shell
### 1. Let's recap some comamnds show in Lesson 2
* Variable 
```bash
x=100               # set variable x to 100
export x=100        # same as above
y="Some String"     # set variable y to "Some String"

export x=           # same as above
unset x             # same as above

```

* Directories & Files
```bash
cd ~/Desktop        # Change to Desktop folder
cd ..               # Go 1 level up from current folder
cd ~                # Go to your home directory (Eg. /home/<your_userid> in linux, /c/Users/<your_userid> in windows)

pwd                 # print your current directory
ls                  # list out content on current folder
ls .                # Same as above
ls -l  .            # Same as above (long format)
ls -la .            # Same as above (long format, with hidden files/directories)

mkdir test          # create directory test
mkdir -p test1/sub1 # create directory test1 and subdirectory sub1
rmdir test          # remove directory test (failed if directory not empty)
rm -rf test         # same as above, but recurively (-r) by force (-f)

touch a.txt         # create file a.txt
rm a.txt            # remove file a.txt
mv a.txt test1      # move file a.txt to directory test1 (if test1 exists)
mv a.txt test1/b.txt    # same as above, but file is saved as b.txt
mv a.txt b.txt      # rename file a.txt to b.txt

cat a.txt           # print all content from file a.txt
less a.txt          # print portion content, but can scroll and search
```

### 2. New Command

* Doumentation
```bash
man ls               # display manual doc for ls command (might not work in git bash)
# This is a comment  # single line comment
: '                  # multi line comment
  This is a 
  multi line 
  comment
  '
```

* Variable expansion 
```bash
a="file1.txt"
echo $a             # print file1.txt
echo ${a}           # same as above
echo ${a:0:1}       # print f (start from 0, end at 1 position)
echo ${a:(-4)}      # show last 4 character - .txt     
```

* Command Substitution
```bash

set a=$(pwd)        # set variable a to pwd output
echo $a
```

* Files
```bash
head -3 a.txt       # show 10 lines from a.txt
tail -3 a.txt       # show 10 lines from a.txt
```

* Input/Output Redirection
```bash
echo "my first line" >> c.txt    # write content to file c.txt (append to file if exists)
echo "my first line" > c.txt     # same as above (overwrite if exists)
```

* Looping
```bash
for i in $(ls .); do echo $i; done      # loop through file listing
```

* Combining commands & Pipe
```bash

echo hello;echo world           # 2 commands in one line
false && echo hello             # nothing to print, execute the subsequent command if the preceding executed successfully/exit status is zero
true && echo hello              # print hello
false || echo hello             # print hello. execute the subsequent command if the preceding executed not successfull/error status not zero
true || echo hello              # print nothing

# Pipe command |
echo -e "First\nSecond\nThird" | grep Second     # output Second
echo -e "First\nSecond\nThird" | grep -i second  # same as above (-i ignore case)

```

* Functions
```bash
    greeting() {                      # declare myfunc function
        echo "hello $1 $2"
    }

    function greeting() {             # Same as above
        echo "hello $1 $2"
    }

    greeting world                    # call function greeting, pass world as parameter ($1) 
    greeting world everyone           # call function greeting, pass world ($1) & everyone($2)
```


         