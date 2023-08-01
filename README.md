##  Basic work with files

- Create directory test1

```console
mkdir test1
```

- Create file test1.txt inside the test1 directory.

```console
cd test1 
touch test1.txt
vim test1.txt
```

-   Create copy of folder test1 with name test2.
  
```console
cp -a test1 test2
```

-    Delete file test1.txt inside test2 directory.

```console
rm -f test2/test1.txt
```

-    Rename test2 folder into directory_without_file

```console
mv test2 directory_without_file
```

-    Insert 'test1' text into test1/test1.txt file.

```console
vim test1/test1.txt > test1
```



-    Insert 'test2' into the end of test1/test1.txt file.
```console
echo "test2" >> test1/test1.txt 
```

-    print the text from the test1/test1.txt file.

```console
cat test1/test1.txt
```

- check the size of test1 directory

```console
du -hs test1
```
## Permissions

-   Create test directory and block access for all to it.
```console
mkdir directory_without_access
chmod 000 directory_without_access
```
-   Try to remove that directory.

```console
rm -rf directory_without_access
I can remove directory
```

-    Create simple script which prints current date. Try to execute it.
```console
vim date.sh 
#!/bin/bash
date
------
bash date.sh
```

## Log checking

-  Count lines in the file test.txt.
```console
wc -l test.txt
```

- Show last 3 lines from the test.txt file. 
```console
tail -3 test.txt
```

-  Hom many uniq IP addresses accessed the website ? 
```console
cat test.txt | awk '{print $1}' | sort | uniq | wc -l
```

-  IP address with most requests.
```console
cat logs.txt | awk '{print $1}' | sort | uniq -c | sort -nr | head -n 1
```

-  Top 3 IP addresses by amount of POST requests.


-  Which IP addresses received 403 error ? 
```console
grep ' 403 ' test.txt | awk '{print $1}'
```

- Task with * . Write script to show which pages Google checked from the website 

## Replace

Replace IP address with most requests on 127.0.0.1 in test.txt file
```console
cat test.txt | awk '{print $1}' | sort | uniq -c | sort -nr | head -n 1
sed -i 's/54.236.1.11/127.0.0.1/g' test.txt
``` 
