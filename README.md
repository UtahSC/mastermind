# mastermind

Mastermind is a two player guessing game. One player creates a sequence of four colors, and the other player attempts to guess the sequence. After each guess, the receive a two-part score describing the correctness of their guess.

In this Kata, we will implement an electronic version of Mastermind. In part 1, we will code the role of codemaster. Part 2 is to build a codebreaker/solver. If you're feeling ambitious, you can start with Part 2, but it is much more difficult.

## Part 1 - Codemaster

The colors available are:
```
Red
Blue
Yellow
Green
Orange
Purple
```

As a Codemaster, you must pick a code, which is a sequence of four colors.  The codebreaker then gets up to 10 guesses to try and determine the code.

You must score each guess based on two factors. First, you need to count the number of colors that are in the correct position in the sequence.  After ?

### Examples

For a generated code of:

`[ Red Green Green Purple ]`

A guess of:

`[ Red Blue Yellow Green ]`

returns a score of `1,1`, because the first `Red` is the correct color and in the correct position, and `Green` is one of the remaining colors.

A guess of: 

`[ Red Blue Yellow Red ]`

returns a score of `1,0`, because the first `Red` is the correct color and in the correct position, and none of the other colors appear in the rest of the sequence.

Note: The sum of the scores is always less than or equal to 4.

## Part 2 - Codebreaker

Write an algorithm that will attempt to solve a code. You can either use the API you built in part 1, or assume the following API for the codemaster:

```
Score Guess(List<Color>);

Score {
integer CorrectColorAndPosition;
integer CorrectColorWrongPosition;
}

Color in Red, Yellow, Blue, Green, Orange, Purple;
```

An algorithm [exists](http://www.cs.uni.edu/~wallingf/teaching/cs3530/resources/knuth-mastermind.pdf) that can solve mastermind in no more than 5 guesses. Other algorithms have been proven to have better average case performance, with worst-case performance of six guesses.

Good luck!
