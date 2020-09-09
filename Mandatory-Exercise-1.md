## Deadline for submission

**Deadline for submission: Friday, September 18, 18.00.**

## Working in teams and use of GitLab

1. Within your study group, you will be assigned to a team of up to four students. You will submit mandatory activity as a team and will jointly receive credit for it. We reserve the right to withhold credit if a member of a team does not contribute to the team effort.
1. We will create a GitLab group for each team, e.g., `Wed10A_1` for each team and invite the members of each team to that group. Only team members, teachers and teaching assistants will have access to material in the group.
1. Each mandatory exercise will stretch over two weeks. During the first week, you will develop code and create merge requests for it on GitLab. In the second week, you will discuss your code and document the results of your discussion on GitLab. This is your delivery. The entire process is illustrate (for two students) in [a video posted on Vimeo](https://vimeo.com/454435193/7421a85233). **Watch this video before you read on, otherwise what follows will probably seem very confusing.**
1. **One** team member creates a GitLab Project (repository) within the team's GitLab group as shown in the video. This team member also adds the `.gitignore` file (as a copy of `gitignore_default` from the `inf200-course-materials/technical`) on the master branch and pushes it back to GitLab.
1. **When committing to Git, make sure that you never commit files from the `.idea` directory!**
1. **After that is done**, all other team members clone the repository to their computers.
1. Each mandatory exercise will consist of four tasks, Task A through Task D. Each team member should prepare code for one of the tasks (but discuss with each other while solving the tasks!).
    1. Create a branch for each task, e.g., called `ex01_taskA` for Task A in Exercise 1.
    1. Push that branch to GitLab.
    1. Create a merge request to the master branch in GitLab.
    1. Document the results of your code review as comments in the merge request.


## The programming tasks

1. Exercise 1 consists of several tasks, where each task requires you to write a single Python script (`*.py` file). 
1. For each task, create a branch with the name of the task (e.g. `ex01_taskA` and a file with the prescribed name.
1. Each Python file shall begin with the following header:

        #!python
        # -*- coding: utf-8 -*-
        
        __author__ = ''
        __email__ = '@nmbu.no'
    where the `__author__` and `__email__` strings shall contain name and email address of the main author of that file.

### Code inspection

Your code must pass code inspection in PyCharm. In particular,

1. PyCharm must show a green check mark in the top right corner of
the editor pane
1. Running code inspection (`Code > Inspect code ...`) shall not
report any problems (it is okay if code inspection complains about typographical
errors in your name)

Note that `Code > Reformat code` can fix a lot of formatting problems for you—use it!


### Task A: Trigonometric table

Filename: `trigtable.py`

Write a program that tabulates sine, cosine and tangent at intervals of 5 degrees. Angles shall be shown in degrees (0 - 360) and radians (0 - 2 pi). The program shall print tidily formatted table.


### Task B: From comprehension to loop

Filename: `comp_to_loop.py`

Create file `comp_to_loop.py`, add the following function definition
and a main section similar to the one in Task A. Then write a function
`squares_by_loop()` that returns the same list as `squares_by_comp()`,
but creates the list using a `for`-loop.

```
#!python

def squares_by_comp(n):
    return [k**2 for k in range(n) if k % 3 == 1]
```


### Task C: Counting letters

Filename: `letter_counts.py`

Write code for the function `letter_freq()` below, so that the program
will print the number of times each letter, digit or symbol appears in
the string passed to `letter_freq()`. Case should be ignored, i.e.,
all letters counted as lowercase letters.

```
#!python

def letter_freq(txt):
    pass

if __name__ == '__main__':
    text = input('Please enter text to analyse: ')

    frequencies = letter_freq(text)
    for letter, count in frequencies.items():
        print('{:3}{:10}'.format(letter, count))
```

A run of this program could look like this:

```
#!bash

Please enter text to analyse: Hi, Jim!
!           1
            1
i           2
h           1
j           1
m           1
,           1
```

As an extra challenge, modify the code printing the table so that
letters are printed in alphabetical order. You can use one of Python's
built in sorting functions and use the ordering provided by that
function.

### Task D: Clean up code

Filename: `tidy_code.py`

Try to understand what the Python program below does. Then copy the
code into file `tidy_code.py`, and make it comprehensible by changing
variable and function names, and maybe also reorganise code.

```
from random import randint as a

__author__ = ''
__email__ = '@nmbu.no'


def b():
    c = 0
    while c < 1:
        c = int(input('Your guess: '))
    return c

def d():
    return a(1, 6) + a(1, 6)

def e(f, g):
    return f == g

if __name__ == '__main__':

    h = False
    i = 3
    j = d()
    while not h and i > 0:
        k = b()
        h = e(j, k)
        if not h:
            print('Wrong, try again!')
            i -= 1

    if i > 0:
        print('You won {} points.'.format(i))
    else:
        print('You lost. Correct answer: {}.'.format(j))
```
