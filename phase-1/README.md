# Phase 1

__ANYTHING WRITTEN HERE OVERRIDES INSTRUCTIONS IN THE HANDOUT__

## Getting Started

1. Choose a language and its corresponding skeleton repo 
    1. [Haskell](https://github.com/6035/haskell-skeleton)
    1. [Java](https://github.com/6035/java-skeleton)
    1. [Scala](https://github.com/6035/scala-skeleton)
1. Set up git on Athena, ideally by ssh'ing into it
1. Go to the 6035 GitHub Organization, and make an empty __PRIVATE__ repo whose name has the format `phase1-<KERBEROS>`. For example if your kerberos is `jchoi5me`, your repo name should be `phase1-jchoi5me`
1. Run the following, as shown in the handout:
    ```bash
    # clone and cd into the repo you just created
    git clone git@github.com:6035/phase1-<GITHUB_USERNAME>.git
    cd phase1-<GITHUB_USERNAME>

    # acquire skeleton code
    git remote add skeleton https://github.com/6035/<LANGUAGE>-skeleton.git
    git pull skeleton master

    # acquire Decaf tests
    git remote add tests https://github.com/6035/tests.git
    git pull tests master

    # run tests
    cd tests/
    ./scanner/test.sh
    ./parser/test.sh
    ```
1. Read the __[HANDOUT](../materials/handouts/02-scanner-parser-project.pdf)__

## Constraints

In addition to the constraints written in the handout, keep the following in mind.

As long as we can run `./build.sh` to build your project and `./run.sh $ARG1 $ARG2 ...` to run your compiler, you can modify those scripts and choose a build system of your own.

__IF WE CLONE YOUR PROJECT ON ATHENA AND THE ABOVE STEPS DO NOT WORK, POINTS WILL BE DEDUCTED__

## Additional Notes

We encourage (not force) you to write a recursive descent parser by hand rather than having Antlr generate one for you.

One reason is that it will be a good learning experience, and you'll get to have a more intimate understanding of parsers and languages in general. A variant of this class, `6.S081`, writes a recursive descent parsers by hand as a part of their project.

Second and the more important reason is that you will have to choose teammates shortly after the completion of this phase. This is for you to be able to get a sense of other students' capabilities as software engineers before having to commit an entire semester to being their teammate. How well someone writes Antlr grammars and lexer rules is not really indicative of how they write software. A recursive descent parser will be a nontrivial amount of code, and will be just about enough code to gauge someone's programming skills and for you to show off your own.

