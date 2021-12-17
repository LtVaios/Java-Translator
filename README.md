# Java-Translator
✔️ This programm takes specifically syntaxed peudocode and translates that code into java code. More details about the syntax are given below.

## Installation / Run
🔨 Download and install the Translator file locally. Then you can compile the programm with:
```
make compile
```
To run the programm and start wriitng pseudocode type:
```
make execute
```
After writing the pseudocode programm, the equivalent java code will be printed to stdout.

## Pseudocode Syntax
✒️ The translator only works with strings. It supports concatenation ("+"), if-else statements, nested if-else staements, string Literals, functions and function calls. It also supports the special keywords "prefix", "suffix" which can be used as 'if' conditions (see examples below). All function definitions must be on top of the programm and all function calls at the end of the programm. Here are some input examples:

```
name() {
  "John"
}

surname() {
  "Johnny"
}

fullname(firsnt_name,sep,last_name) {
  firts_name + sep + last_name
}

name()
surname()
fullname(name() + " " + surname())
```
```
name() {
  "John"
}

repeat(name) {
  name + name
}

cond_repeat(y,x) {
  if(y prefix "word")
      if("word" prefix y)
          repeat(x)
      else
          x
  else
      x
}

cond_repeat("word",name())
cond_repeat("random","Michael")

```

## Code info
All the nessecary code for this translator is written inside parser.cup. CUP files are given a lexer and a grammar and run based on these 2 and print stuff in stdout based on each grammar line indicator given by me. For example when the top statement called 'programm' is called at the start of the parsing then I code it to always print 2 java functions calculating prefix and suffix because they are needed in every type of input programm. More info about java.cup you can find at: http://www2.cs.tum.edu/projects/cup/.
The programm is also using a custom lexical analyzer generator made with jflex: https://www.jflex.de/. <br />

PS: The grammar I made is LALR(1). 

## Built with
![](ignore/jv.png)
![](ignore/jflex.PNG) <br />
![](ignore/cup.PNG)
