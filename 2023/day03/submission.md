
# Basic Linux Commands

1. To view what's written in a file.
    - ``` cat filename ``` 
    
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat > fruits.txt
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ ls
fruits.txt
```


2. To change the access permissions of files.
   
    - ``` chmod 777 foldername ``` 

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ chmod 777  fruits.txt
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ ls -ltr
total 0
-rwxrwxrwx 1 rajas_pawar rajas_pawar 0 Dec 18 20:16 fruits.txt
```

3. To check which commands you have run till now.

   - ``` history ``` 

```
rajas_pawar@LAP181:~/DevOps/Learning/Day3$ history
 1 ls
 .
 .
 1151  cat fruits.txt
 1152  cat > fruits.txt
 1153  ls
 1154  chmod 777  fruits.txt
 1155  ls -ltr
 1156  history
```


4. To remove a directory/ Folder.

      - ``` rm filename ``` 
      
    -  ``` rmdir foldername ```
```  
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ mkdir myfolder
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ ls
fruits.txt  myfolder
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ rmdir myfolder
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ ls
fruits.txt
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ rm fruits.txt
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ ls

```

5. To create a fruits.txt file and to view the content.
    - ``` cat > fruits.txt ``` 
    -  ```  cat fruits.txt ``` 
 ```  
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat > fruits.txt
Apple
Mango
Banana
Cherry
Kiwi
Orange
Guava
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat fruits.txt
Apple
Mango
Banana
Cherry
Kiwi
Orange
Guava
```
6. Add content in devops.txt

   - ``` cat > devops.txt ```

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat > devops.txt
Apple
Mango
Banana
Cherry
Kiwi
Orange
Guava
```

7. To Show only the top three fruits from the file

   -```head -n 3 devops.txt```

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ head -n 3 devops.txt
Apple
Mango
Banana
```

8. To Show only the bottom three fruits from the file

   -```tail -n 3 devops.txt```

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ tail -n 3 devops.txt
Kiwi
Orange
Guava
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$
```

9. To create another file Colors.txt and to view the content

   -```cat > Colors.txt```

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat > Colors.txt
Red
Pink
White
Black
Blue
Orange
Purple
Grey
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ cat Colors.txt
Red
Pink
White
Black
Blue
Orange
Purple
Grey
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$
```
10. To find the difference between fruits.txt and Colors.txt files

    -```diff fruits.txt Colors.txt```

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day3$ diff fruits.txt Colors.txt
1,5c1,5
< Apple
< Mango
< Banana
< Cherry
< Kiwi
---
> Red
> Pink
> White
> Black
> Blue
7c7,8
< Guava
---
> Purple
> Grey
```

#### The diff command output uses specific symbols and numbers to indicate differences between the two files:

- Line Numbers: Show the line range in each file that differs.
- Symbols:
  
      <: Content from the first file (fruits.txt).
      >: Content from the second file (Colors.txt).
      c: Indicates that a change (replacement) occurred.
      d: Indicates a deletion.
      a: Indicates an addition.

### Detailed Breakdown
1. 1,5c1,5
This part indicates that lines 1 to 5 in fruits.txt are replaced with lines 1 to 5 in Colors.txt.

From fruits.txt:
Apple
Mango
Banana
Cherry
Kiwi

To Colors.txt:
Red
Pink
White
Black
Blue

| Explanation: The first five lines of fruits.txt are completely different from the first five lines of Colors.txt.


2. 7c7,8
This part indicates that line 7 in fruits.txt is replaced by lines 7 and 8 in Colors.txt.

From fruits.txt:
Guava

To Colors.txt:
Purple
Grey

| Explanation: The last line in fruits.txt (line 7) is replaced by two lines in Colors.txt (lines 7 and 8).

 
