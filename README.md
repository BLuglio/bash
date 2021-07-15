# bash
Useful bash scripts and linux commands

untar package:
```
tar xvzf PACKAGENAME.tar.gz
```

find file:
```
sudo find -name "filename.ext"
                "file.?"      // file.1, file.2, file.a
		"file.[a-d]"  // file.a, file.b, file.c, file.d
		"file.[ac]"   // file.a, file.c
		"file.[^ab]"  // all except: file.a, file.b
```

change directory/file permissions:
```
chmod -R o=rwx /dir   // read, write, exec for everyone
chmod -R u=rwx /dir   // read, write, exec for user only
chmod -R g=rwx /dir   // read, write, exec for group only
```

script to executable:
```
chmod +x script.sh
```

pipe & write example:
```
  sort names.txt | uniq > sortednames.txt     // overwrite
  sort names.txt | uniq >> sortednames.txt    // append to file
```

error check:
```
if [ -z $1 ]; then                      # if $1 has length zero
        echo "No pattern given."
        echo "Usage: $0 <pattern>"      # $0 contains the name of the script
        exit
fi
```

script that moves all files containing a certain pattern to a second directory
```
firstdir=dir1
seconddir=dir2

for i in 'grep -l matchpattern $firstdir/*'; do       # find the names of files that contain the string matchpattern
        mv $i $seconddir
        echo $i
done
```
