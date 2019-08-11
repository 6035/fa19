# 6.035 Computer Language Engineering

Any and all information about 6.035 Fall 2019!

## Schedule

TODO

## General Administrivia

### Course Staff

- Professor
    - Martin Rinard <rinard@csail.mit.edu>
- TA's
    - Jack Choi <jchoi5me@mit.edu>
    - Jackie Bredenberg <jamb@mit.edu>

### MIT Catalog Description

- Prereq -- `6.004` and `6.031`
- Level -- `U`
- Units -- `4-4-4`

Analyzes issues associated with the implementation of higher-level programming languages. Fundamental concepts, functions, and structures of compilers. The interaction of theory and practice. Using tools in building software. Includes a multi-person project on compiler design and implementation.

### Recommended Texts

6.035 has no officially required textbook. All of the material you need is taught in class, with the exception of the documentation for your implementation language and associated libraries. However, the following books may be helpful in implementing various components of your compiler, and are available from MIT libraries.

```txt
Modern Compiler Implementation in Java (Tiger Book)
Andrew W. Appel and Jens Palsberg
Cambridge University Press, 2002
```

Many other resources such as technical papers, interesting and useful blog posts, and reference guides are available on the references page.

### Communication

We will distribute assignments and make all announcements ~~on the course web site~~ via Piazza and GitHub page. Important announcements will also be made via email. 

Since lecture dates are not all finalized at the start of the semester, please pay attention to the schedule.

### Grading and attendance policy

Your grade in 6.035 is based upon four components: your compiler, two quizzes, and the mini-quizzes at the beginning of every lecture. You must therefore attend all lectures in order to take the mini-quizzes and receive a full grade.

For more information on the way the compiler project is graded, see the projects overview handout from the first recitation.

### Late policy

We expect you to attend all quizzes and submit the project on time. For extensions under extenuating circumstances (e.g., you are sick for a week, family emergencies), we require a letter from one of the student deans at S^3.

### Collaboration

Although you may discuss the projects with anybody, you must develop the code yourself. For the scanner/parser project, you must develop your code alone. On all subsequent projects, you should work with your team members, but you may not develop or share any code with other teams.

You may collaborate on the mini-quizzes, but you may not collaborate with anybody on the full quizzes; doing so will result in a failing grade.

Do not post your lab or homework solutions on publicly accessible web sites or file spaces; this enables cheating for students in future years.

### Compiler Building and Running

We will use the software provided by the Athena infrastructure to evaluate each group project. The project skeletons contain the scripts that will automatically build and run your projects.

The submitted project should be self-contained. With the exception of the languages and libraries provided by the Athena infrastructure, all code and libraries (when applicable; see the next section) should be contained within the submitted archive.

Make sure to build and run your compiler on the Athena infrastructure before submitting it for evaluation. If we are not able to automatically build or run your compiler using the scripts provided with the project skeletons, it will incur a 25% penalty on the number of points for this project.

### Third-party Libraries

In 6.035, you build a compiler almost entirely from scratch. There are a few allowed exceptions: you may use one of the approved parser generators, described in the first project & athena handouts. You may use various language APIs for working with collections and data types. However, there are some restrictions on that. For example, users of Haskell may not use Haskell's Data.Graph or Compiler packages.

Any libraries beyond the Java API or basic Scala libraries must be approved by the TA. We will not allow more advanced libraries, such as the PackratParsers package. In general, if you are unsure of whether or not you are allowed to use a piece of software, ask the TA.

### Class meetings

Lectures will be held on Mondays through Fridays from 11:00am to 12:00pm in room 3-370 MWF, and room 4-149 TR. There is not a lecture on every such day; for details, see the schedule.

### Contact

For all general questions and/or concerns, please post on Piazza.

If the matter is private, please email the TA's directly.

### Office Hours and Relectures

~~Tuesday relectures are held on Tuesdays from 5-6 pm in room 2-142 and Thursday relectures are held on Thursdays from 5-6 pm in room 2-135.~~

Email the TAs to schedule a relecture ~~for other class days. Office hours are Tuesdays from 6-7 pm in room 2-142 and Thursdays from 6-7 pm in room 2-135. On Tuesdays and Thursdays that lecture doesn't occur, office hours are scheduled during relecture time, i.e., they are held Tuesdays from 5-7 pm in room 2-142 and Thursdays from 5-7 pm in room 2-135.~~

We will organize additional office hours before each of the quizzes and leading up to the due dates of class projects. We will announce the schedule of these office hours during the class.

##  Reference Materials

This section contains a number of useful and/or interesting references selected by the staff. You are not expected to know most of the material on this page for quizzes or for implementing your compiler; however, you may find it interesting and helpful.

### Official References

- Decaf language spec TODO link
- `x86_64` architecture guide http://6.035.scripts.mit.edu/fa18/x86-64-architecture-guide.html
- The complete Intel x64 manual http://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-software-developer-manual-325462.pdf
- Intel x64 Optimization Reference Manual http://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-optimization-manual.pdf

#### Provided During Exams

- [x64 cheat sheet](https://cs.brown.edu/courses/cs033/docs/guides/x64_cheatsheet.pdf) -- lists and tables detailing registers and assembly commands
- [Introduction to x86-64 Assembly](https://www3.nd.edu/~dthain/courses/cse40243/fall2015/intel-intro.html) -- more info on registers and some assembly examples.

### Unofficial References

Interesting blog posts, papers, etc

- Overviews
    - [LLVM compiler architecture](http://www.aosabook.org/en/llvm.html)
    - [GCC compiler architecture](http://en.wikibooks.org/wiki/GNU_C_Compiler_Internals/GNU_C_Compiler_Architecture)
- Blogs
    - [Russ Cox's Blog](http://research.swtch.com/) -- Russ is one of the developers of Google Go, a pretty interesting language.
    - [Ian Wienand's Blog](http://www.technovelty.org/) -- Whoever he is, he writes about compiler and language internals, the magic black box that is the linker, and more
    - [Matt Might's Blog](http://matt.might.net/articles/) -- Matt is a professor at the University of Utah and has written some very interesting articles (e.g. "Yacc is dead")
- Papers
    - [Register Allocation & Spilling via Graph Coloring](http://dl.acm.org/citation.cfm?id=806984) -- G.J. Chaitin / 1982. Great (short) paper on simple register allocation.
    - [Iterated Register Coalescing](http://dl.acm.org/citation.cfm?id=229546) -- Lal George / 1996. Presents improvements/alternative to Chaitin's design. If Chaitin-style (+/-Briggs) register allocation isn't enough for you, this paper is a good read - actually, it's a good read anyway, to understand the tradeoffs
    - [Superword Level Parallelism](http://dl.acm.org/citation.cfm?id=358438) combined with loop unrolling, a simple way to implement a vectorizing compiler
- Miscellaneous
    - [Scala Patterns for Compiler Design](https://gist.github.com/rcoh/4992969)
    - `6.823 Advanced Computer Architecture` [lecture notes](http://csg.csail.mit.edu/6.823/lecnotes.html)
