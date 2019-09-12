# 6.035 Computer Language Engineering FA19

Any and all information about 6.035 Fall 2019!

There are two websites for 6.035 fa19:
1. [this page](https://github.com/6035/fa19)
1. [Piazza][piazza]

__WE WILL MAKE ALL ANNOUNCEMENTS VIA PIAZZA, SO MAKE SURE THAT YOU ENROLL__

If neither site has the information you need, you should [email the TA's directly](#course-staff)

## Table of Contents

1. [6.035 Computer Language Engineering](#6035-computer-language-engineering)
    1. [Schedule](#schedule)
    1. [General Administrivia](#general-administrivia)
        1. [Course Staff](#course-staff)
        1. [MIT Catalog Description](#mit-catalog-description)
        1. [Recommended Texts](#recommended-texts)
        1. [Communication](#communication)
        1. [Grading and attendance policy](#grading-and-attendance-policy)
        1. [Late policy](#late-policy)
        1. [Collaboration](#collaboration)
        1. [Compiler Building and Running](#compiler-building-and-running)
        1. [Third-party Libraries](#thirdparty-libraries)
        1. [Class meetings](#class-meetings)
        1. [Contact](#contact)
        1. [Office Hours and Relectures](#office-hours-and-relectures)
    1. [Reference Materials](#reference-materials)
        1. [Official References](#official-references)
            1. [Provided During Exams](#provided-during-exams)
        1. [Unofficial References](#unofficial-references)

## Schedule

[Official MIT Calendar](https://registrar.mit.edu/calendar)

```txt
                                            2019
     September                October                 November                December
Su Mo Tu We Th Fr Sa    Su Mo Tu We Th Fr Sa    Su Mo Tu We Th Fr Sa    Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7           1  2  3  4  5                    1  2     1  2  3  4  5  6  7
 8  9 10 11 12 13 14     6  7  8  9 10 11 12     3  4  5  6  7  8  9     8  9 10 11 12 13 14
15 16 17 18 19 20 21    13 14 15 16 17 18 19    10 11 12 13 14 15 16    15 16 17 18 19 20 21
22 23 24 25 26 27 28    20 21 22 23 24 25 26    17 18 19 20 21 22 23    22 23 24 25 26 27 28
29 30                   27 28 29 30 31          24 25 26 27 28 29 30    29 30 31
```

Note: `L4: parsing~55` means that the topic was `parsing` and we covered up to slide `55`.

|                 | Monday | Tuesday | Wednesday | Thursday | Friday |
| :-:             | :-:    | :-:     | :-:       | :-:      | :-:    |
| `09/02 - 09/06` | | | __FIRST DAY__<br>[L1: overview][lec01]<br>[piazza]<br>[project info]<br>[survey][gform-1] | [L2: regex][lec02] | [L3: regex][lec02] |
| `09/09 - 09/13` | P1 INFO SESS<br>[L4: grammar~55][lec02]<br>[course tools]<br>[decaf spec]<br>[P1 release] | [L5: grammar~62][lec02]<br>[L5: parsing~46][lec03] | [L6: parsing~72][lec03] | L7: parsing | |
| `09/16 - 09/20` | | | __P1 DUE__ | P2 INFO SESS | Career Fair |
| `09/23 - 09/27` | __SUBMIT TEAM__<br>L8 | L9 | L10 | L11 | L12 |
| `09/30 - 10/04` | L13 | L14 | | | __P2 DUE__<br>P3 INFO |
| `10/07 - 10/11` | L15 | L16 | L17 | | __QUIZ 1__ |
| `10/14 - 10/18` | Columbus Day | Columbus Day | L18 | L19 | |
| `10/21 - 10/25` | | | | | Family Weekend |
| `10/28 - 11/01` | | | __P3 DUE__<br>P4 INFO SESS | L20 | L21 |
| `11/04 - 11/08` | L22 | L23 | | | |
| `11/11 - 11/15` | | __P4 DUE__<br>P5 INFO SESS | L24 | L25 | L26 |
| `11/18 - 11/22` | L27 | L28 | __DROP DATE__ | | |
| `11/25 - 11/29` | | | | Thanksgiving | Thanksgiving |
| `12/02 - 12/06` | | __QUIZ 2__ | | __CHECKPOINT__ | |
| `12/09 - 12/13` | | __P5 DUE__ | __LAST DAY__<br>__DERBY__ | | |

<!--- others --->
[piazza]: https://piazza.com/mit/fall2019/6035
[gform-1]: https://docs.google.com/forms/d/e/1FAIpQLScRu9Sx9VTtfuxup5NaDhYXrFnFmRG1ivvsFWiE9yazulOrIA/viewform

<!--- project phases --->
[phase-1]: phase-1/

<!--- handouts --->
[course tools]: materials/handouts/01-athena.pdf
[project info]: materials/handouts/01-project-overview.pdf
[decaf spec]: materials/handouts/01-decaf-spec.pdf
[P1 release]: materials/handouts/02-scanner-parser-project.pdf


<!--- miniquizzes --->

<!--- exams and answer keys --->
<!---__QUIZ 1__<br>[2011][11-e1], [key][11-k1]<br>[2013][13-e1], [key][13-k1]<br>[2014][14-e1], [key][14-k1]<br>[2016][16-e1], [key][16-k1]<br>[2017][17-e1], [key][17-k1]<br>[2018][18-e1], [key][18-k1]--->
[11-e1]: materials/exam/2011-exam1.pdf
[11-k1]: materials/exam/2011-exam1-key.pdf
[13-e1]: materials/exam/2013-exam1.pdf
[13-k1]: materials/exam/2013-exam1-key.pdf
[14-e1]: materials/exam/2014-exam1.pdf
[14-k1]: materials/exam/2014-exam1-key.pdf
[16-e1]: materials/exam/2016fa-exam1.pdf
[16-k1]: materials/exam/2016fa-exam1-key.pdf
[17-e1]: materials/exam/2017fa-exam1.pdf
[17-k1]: materials/exam/2017fa-exam1-key.pdf
[18-e1]: materials/exam/2018fa-exam1.pdf
[18-k1]: materials/exam/2018fa-exam1-key.pdf

<!--- lecture slides --->
[lec01]: materials/lecture/lec01-f19-intro.pdf
[lec02]: materials/lecture/lec02-f19-regex-grammar.pdf
[lec03]: materials/lecture/lec03-f19-top-down-parsing.pdf

## General Administrivia

### Course Staff

- Professor
    - Martin Rinard <rinard@csail.mit.edu>
- TA's
    - Jackie Bredenberg <jamb@mit.edu>
    - Jack Choi <jchoi5me@mit.edu>

### MIT Catalog Description

- Prereq -- `6.004`, `6.031`
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

We will distribute assignments and make all announcements via [Piazza][piazza] and GitHub (this) page. Important announcements will also be made via email.

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

Lectures:
- 11am-12pm MWF in 32-144.
- 11am-12pm TR in 66-144

To find out whether there is lecture on a given day, check calendar above.

### Contact

For all general questions and/or concerns, please post on Piazza.

If the matter is private, please email the TA's directly.

### Office Hours and Relectures

Office Hours:
- Tuesday's 4pm-6pm in 34-304
- additional ones available via request

Relecture:
- Monday's 7pm-9pm in 34-304
- Thursday's 4pm-5pm in 34-304
- additional ones available via request

Note that relectures are only held if students email the TA's in advance to request one.

We will have additional office hours before each quiz and each phase of the project.

## Reference Materials

This section contains a number of useful and/or interesting references selected by the staff. You are not expected to know most of the material on this page for quizzes or for implementing your compiler; however, you may find it interesting and helpful.

### Official References

1. Decaf language spec TODO link
1. [`x86_64` architecture guide](http://6.035.scripts.mit.edu/fa18/x86-64-architecture-guide.html)
1. The complete [Intel x64 manual](http://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-software-developer-manual-325462.pdf)
1. [Intel x64 Optimization Reference Manual](http://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-optimization-manual.pdf)

#### Provided During Exams

1. [x64 cheat sheet](https://cs.brown.edu/courses/cs033/docs/guides/x64_cheatsheet.pdf) -- lists and tables detailing registers and assembly commands
1. [Introduction to x86-64 Assembly](https://www3.nd.edu/~dthain/courses/cse40243/fall2015/intel-intro.html) -- more info on registers and some assembly examples.

### Unofficial References

Interesting blog posts, papers, etc

1. Overviews
    1. [LLVM compiler architecture](http://www.aosabook.org/en/llvm.html)
    1. [GCC compiler architecture](http://en.wikibooks.org/wiki/GNU_C_Compiler_Internals/GNU_C_Compiler_Architecture)
1. Blogs
    1. [Russ Cox's Blog](http://research.swtch.com/) -- Russ is one of the developers of Google Go, a pretty interesting language.
    1. [Ian Wienand's Blog](http://www.technovelty.org/) -- Whoever he is, he writes about compiler and language internals, the magic black box that is the linker, and more
    1. [Matt Might's Blog](http://matt.might.net/articles/) -- Matt is a professor at the University of Utah and has written some very interesting articles (e.g. "Yacc is dead")
1. Papers
    1. [Register Allocation & Spilling via Graph Coloring](http://dl.acm.org/citation.cfm?id=806984) -- G.J. Chaitin / 1982. Great (short) paper on simple register allocation.
    1. [Iterated Register Coalescing](http://dl.acm.org/citation.cfm?id=229546) -- Lal George / 1996. Presents improvements/alternative to Chaitin's design. If Chaitin-style (+/-Briggs) register allocation isn't enough for you, this paper is a good read - actually, it's a good read anyway, to understand the tradeoffs
    1. [Superword Level Parallelism](http://dl.acm.org/citation.cfm?id=358438) combined with loop unrolling, a simple way to implement a vectorizing compiler
1. Miscellaneous
    1. [Scala Patterns for Compiler Design](https://gist.github.com/rcoh/4992969)
    1. `6.823 Advanced Computer Architecture` [lecture notes](http://csg.csail.mit.edu/6.823/lecnotes.html)
