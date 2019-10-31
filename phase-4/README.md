# Dataflow Optimizations Assignment

__DUE: Tue Nov 12 23:59:59 EDT 2019__

Run `git pull tests master` to get started!

## Table of Contents

1. [Dataflow Optimizations Assignment](#dataflow-optimizations-assignment)
    1. [Overview](#overview)
    1. [What to Hand In](#what-to-hand-in)
    1. [FAQ](#faq)

## Overview

For this part of the project, you will add dataflow optimizations to your compiler. __At the very least, you must implement one of the first three global dataflow optimizations below.__ All other optimizations listed below are optional. You may also wait until the next project to implement them if you are going to; there is no requirement to implement more than one dataflow optimizations in this project. We list them here as suggestions since past winners of the compiler derby typically implement each of these optimizations in some form. You are free to implement any other optimizations you wish. Note that you will be implementing register allocation and other assembly level optimizations for the next project, so you don't need to concern yourself with it now.

1. __Global CSE (Common Subexpression Elimination)__: Identification and elimination of redundant expressions using the algorithm described in lecture (based on available-expression analysis). See 8.3 and 13.1 of the Whale book, 10.6 and 10.7 in the Dragon book, and 17.2 in the Tiger book.
1. __Global Copy Propagation__: Given a `copy` assignment like `x = y`, replace uses of `x` by `y` when legal (the use must be reached by only this def, and there must be no modification of `y` on any path from the def to the use).  See 12.5 of the Whale book and 10.7 of the Dragon book.
1. __Dead Code Elimination__: Dead code elimination is the detection and elimination of code which computes values that are not
subsequently used. This is especially useful as a post-pass to constant propagation, CSE, and copy propagation. See the 18.10 ofthe Whale book and 10.2 of the Dragon book.

The following are other useful dataflow optimizations that are useful to implement, but not required for this stage of the project.

1. __Global Constant Propagation and Folding__: Compile-time interpretation of expressions whose operands are compile time constants. See the algorithm described in 12.1 of the Whale book.
1. __Loop-invariant Code Motion (code hoisting)__: Moving invariant code from within a loop to a block prior to that loop. See 13.2 of the Whale book and 10.7 of the Dragon book.
1. __Unreachable Code Elimination__: Unreachable code elimination is the conversion of constant conditional branches to equivalent unconditional branches, followed by elimination of unreachable code. See 18.1 of the Whale book and 9.9 of the Dragon book.

The following are not generally considered dataflow optimizations. However, they can increase the effectiveness for the transformations listed above.

1. __Algebraic Simplification and Reassociation__: Basic algebraic simplifications described in class. This includes simplifying the following rules:
    ```hs
    a + 0      -> a
    a - 0      -> a
    a * 1      -> a
    b == true  -> b
    b != false -> b
    ...
    ```
    You may find it useful to canonicalize expression orders, especially if you choose to implement CSE. See 12.3 of the Whale book and 10.3 of the Dragon book.
1. __Strength reductions__: Algebraic manipulation of expressions to use less expensive operations. This includes the following transformations that convert multiplying constants into bit shifts i.e.: `a * 4 -> a << 2` and include turning multiplication operations from within a loop into sum operations.
1. __Inline Expansion of Calls__: Replacement of a call to procedure `P` by inline code derived from the body of `p`. This can also include the conversion of tail-recursive calls to iterative loops. See 15.1 and 15.2 of the Whale book.

You will want to think carefully about the order in which optimizations are performed. You may want to perform some optimizations more than once.

All optimizations (except inline expansion of calls) should be done at the level of a single method. Be careful that your optimizations do not introduce bugs in the generated code or break any previously-implemented phase of your compiler. Needless to say, it would be foolish not to do regression testing using your existing test cases. __Do not underestimate the difficulty of debugging this part of the project__.

As in the code generation project, your generated code must include instructions to perform the runtime checks listed in the language specification. It is desirable to optimize these checks whenever possible (CSE can be used to eliminate array bounds tests). Note that the optimized program must report a runtime error for exactly those program inputs for which the corresponding unoptimized program would report a runtime error (and the runtime error message must be the same in both cases). However, we allow the optimized program to report a runtime error earlier than it might have been reported in the unoptimized program.

## What to Hand In

We do not need a design description for this phase; make the wripteup a simple status report of how you are doing.

Your compiler's command line interface must provide the following interface for turning on each optimization individually. Something similar should be provided for every optimization you implement. Document the names given to each optimization not specified here.

1. `--opt=cse` turns on common subexpression elimination only
1. `--opt=cp` turns on copy propagation optimization only
1. `--opt=cp,cse` turns on copy propagation optimization and common subexpression elimination only
1. `--opt=all` turns on all optimizations

This is the interface provided by CLI.opts / optnames facility in the Java and Scala skeletons. See the source for more details. A similar mechanism is provided in the Haskell skeleton. For the full command-line specification, see the project overview handout.

You should be able to run your compiler from the command line with:
```bash
./run.sh --target=assembly $FILE_NAME           # no optimizations
./run.sh --target=assembly --opt=all $FILE_NAME # all optimizations
```

Your compiler should then write a x86-64 assembly listing to standard output, or to the file specified by the -o argument.

A reminder that this part of the project won't be graded until you submit your final compiler, but if your team would like feedback, please submit by the deadline listed at the top of this file.

## FAQ

> How do I test my compiler for correctness? i.e. test if my generated assembly works

1. Use [ideas from 6.031](https://web.mit.edu/6.031/www/fa19/classes/03-testing/)
1. Use `tests/dataflow/test.sh` like before
    1. You can run `./test.sh --parallel` to run tests in parallel. Note that this may sometimes throw out-of-memory errors but will run significantly faster

> How do I check that my optimizations are working?

1. Use [ideas from 6.031](https://web.mit.edu/6.031/www/fa19/classes/03-testing/)
1. Write __SMALL__ decaf programs and visually inspect to see if your optimizations took place
    1. This is easy to do for optimizations like dead code elimination
1. Benchmark for performance: we provided you `tests/dataflow/bench.sh` to allow you to do some easy benchmarking. We use [hyperfine](https://github.com/sharkdp/hyperfine), in case you are interested to look into it more!
    ```bash
    ./bench.sh input/cp-01.dcf                  # pass one file
    ./bench.sh input/cp-01.dcf input/cp-02.dcf  # pass arbitrarily many
    ```
    1. Note that all tests that we have provided you thus far are super small, and they run in less than 5 milliseconds. This makes benchmarking inaccurate and somewhat pointless
    1. We encourage you to write your own decaf programs that take a long time to run, on the order of seconds, and use `bench.sh` on those files.
