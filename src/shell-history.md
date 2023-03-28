# Shell History

## Run the last Command as Root
```bash
sudo !!
su -c "!!" # this exclamation mark syntax is called event designator.
```

## Repeat the Last Command That Started with a given String

***Syntax***: `!<string>`

***Explain***: recall the most recent command that begins with <string>.

```bash
df -Th
!d #output: df -Th
```

## Reuse the Second Word (First Argument) from the previous Command
***Syntax***: `!^`

***Explain***: if you need to grab the second word from the previous command.

```bash
host www.google.com 8.8.8.8
ping -c1 "!^" #output is ping -c1 www.google.com
```

## Reuse the Last Word (Last Argument) from the previous Command

***Syntax***: `!$`

***Explain***: if you need to grab the last word from the previous command.

```bash
unzip backup.zip
rm "!$" #output rm backup.zip
mv cover-sheet.doc report
du -sh "!$"
```

## Reuse the Nth word from a previous Command

***Syntax***: `!!:N` `<event-designator>:<number>`
**Explain**: to access a word in the previous command.

```bash
avconv -i screencast.mp4 podcast.mp3
mv "!!:2" converted/ #output is mv screencast.mp4 converted/
```

## Repeat the previous Command while substituting a String

**Syntax**: `^<string1>^<string2>^`
**Explain**: This little trick is great for quickly correcting typing mistakes. if you omit `^<string2>^`, then `<string> `will be removed from the previous command.

```bash
grpe jason /etc/passwd
^pe^ep
grep jason /etc/passwd
grep rooty /etc/passwd
^y
grep root /etc/passwd
```

## Reference a Word of the Current Command and Reuse It

**Syntax:** `!#:N`

**Explain:** The `!#` event designator represents the current command line, while the `:N` word designator represents a word on the command line.

```bash
mv Working-with-Files.pdf Chapter-18-!#:1
mv Working-with-Files.pdf Chapter-18-Working-with-Files.pdf #output
```

## Save a Copy of Your Command Line Session

**Syntax:** script

**Explain:** If you want to document what you see on your screen, use the script command. The script command captures everything that is printed on your terminal and saves it to a file.

## Find out Which Commands You Use Most Often

**Syntax:** `history | awk '{print $2}' | sort  | uniq -c | sort -rn | head`

**Explain:** To get a list of the top ten most used command in your shell history.

## Clear Your Shell History

**Syntax:** `history -c`

**Explain:** To clear your shell history.
