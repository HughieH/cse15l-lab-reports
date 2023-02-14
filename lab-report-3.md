# Lab Report 3
> Written by Hou Wai Wan for CSE 15L Winter 2023

## Comman-line options for the "find" command

1) -size

`find ./written_2/ -size +0M`

**Output:**

![image](images/Report3_size_ex1.png)

`find ./written_2/ -size +1M`

**Output:**

![image](images/Report3_size_ex2.png)

2) -name

`find ./written_2/ -name "China-History.txt"`

**Output:**

![image](images/Report3_size_ex3.png)

`find ./written_2/ -name "*.txt"`

**Output:**

![image](images/Report3_size_ex4.png)

3) -delete

`find ./written_2/ -name "China-History.txt" -delete`

**Output:**

![image](images/Report3_size_ex5.png)

`find ./written_2/ -name "Nepal-History.txt" -delete`

**Output:**

![image](images/Report3_size_ex5.png)

4) -iname

`find . -iname "*.txt"`

**Output:**

![image](images/Report3_size_ex6.png)

`find ../berlitz2 -iname "*.txt"`

**Output:**

![image](images/Report3_size_ex7.png)
