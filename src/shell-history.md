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
**Explain***: to access a word in the previous command.

```bash
avconv -i screencast.mp4 podcast.mp3
mv "!!:2" converted/ #output is mv screencast.mp4 converted/
```

## Repeat the previous Command while substituting a String
