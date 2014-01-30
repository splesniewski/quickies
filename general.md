quickies/general
========

* scan for CDP packet
'''shell
linux# tcpdump -nn -v -i eth0 -s 1500 -c 1 'ether[20:2] == 0x2000' 
'''

* convert local date to UTC
'''shell
linux$ date --utc --date='@'$(date +%s --date='2012-03-21 15:35')
'''

* list all files in a directory, sorted by date

Useful when 'ls -altr $(find ./ -type f -print)' has too many args.

'''shell
linux$ find . -type f -print0 | xargs -0 stat --format '%Y %y %n'| sort -nr | head -32
linux$ find ./ -type f  -printf "%T@ %t %p\n" | sort -nr | head -32
'''

'''shell
osx$ find ./ -type f -print0 | xargs -0 stat -f "%m %N" | sort -nr  | head
'''

* extract OSX webarchive
'''shell
osx$ textutil -convert html webpage.webarchive
'''
