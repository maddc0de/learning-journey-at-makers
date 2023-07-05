# PRECOURSE

## week 1 - Command Line, GIT for Version Vontrol

-----

### Goals

* To be able to use command line commands, such as `ls`, `pwd`, and `cd`
* To be able to use switches to enhance command abilities (parameters that start with a `-` are often called switches)
* To be able to manipulate files from the command line (`cat`, `mv`, `cp` etc)
* To be able to modify permissions in a filesystem
* To be able to manage code versioning with Git and GitHub

### Evidence

* [Command Line Mystery](https://github.com/maddc0de/clmystery) - I used AWS Cloud9 to work through this challenge.

### Resources and other information

* [Vim cheatsheet](https://devhints.io/vim)
* UNIX-based computer are Mac, any Linux including Ubuntu, Cloud9 running Linux, etc., other PCs running Windows
* `ls -lA` command is for listing hidden files (`-l` stands for 'long format', `-A` stands for 'all files')
* `rm -i` will prompt to confirm what file you want to delete `-i` stands for 'interactive'
* `cp` takes two parameters, first is the file to be copied and second is the new file that will be created from it
* `mv` takes two parameters, moves the file but can also be used to rename a file when new destination is not provided
* `cat` `more` `less` `tail`- commands to view files in the terminal
* **Streams** every computer has at least three "standard streams" (input stream, output stream and error stream). Streams are how the programs sends outputs and receives outputs.
* **Pipes** (`|` symbol is known as a "pipe") allows redirection of streams
* **Wildcards**

-----
-----

## week 2-3 - Ruby with Mastery Learning

-----

### Goals

* Utilise irb as a Read-Eval-Print-Loop (REPL) to experiment with Ruby.
* String: Define 'String' as an object and effectively use it.
* Variables: Understand and utilize variables for value assignment and different types of values.
* Methods: Grasp methods as a way to automate Ruby commands, promote DRY code, and solve problems.
* Booleans: Comprehend 'boolean' as true or false, and recognize 'truthy' and 'falsy' concepts.
Arrays: Define arrays as indexed collections, use square-bracket notation, and employ methods and iterators.
* Control Flows: Utilize if/else statements, inline if statements, else statements, and ternary operators effectively.
* Symbols: Define Symbols as immutable objects, understand their memory efficiency, and use them in hashes.
Hashes: Define hashes as 'dictionaries', understand their structure, and use them effectively.
* Blocks: Understand block structure and their usage in Ruby for improved readability.
* Recursion: Define recursion, avoid infinite loops, and use it to avoid nested loops.
* User Input: Get user input using gets, sanitize with chomp and chomp! methods.
* Gems: Define Ruby gems as reusable libraries, understand their usage, location, and installation.
Procs: Define Procs as 'anonymous methods', understand their relationship with lambdas, and use them for metaprogramming.
* Lambdas: Understand the structure and use of lambdas as 'anonymous methods' in solving metaprogramming problems.

### Evidence

* [10 chapters with mastery quizzes in Ruby](https://github.com/maddc0de/mastery-quizzes)

### Resources and other information

* PARALLEL ASSIGNMENT
* SHOVEL OPERATOR - used to add new elements to an array

```ruby
names = ["Jack", "John"]
names << "Alice"
names #=> ["Jack", "John", "Alice"] 
```

* [Bizarre and entertaining Ruby Tutorial](http://poignant.guide/)
* [Ruby methods cheatsheet](https://overapi.com/ruby)

-----
-----

## week 4 - Building Command Line Application, TDD, Pair-Programming

-----

### Goals

* Pair-Program on FizzBuzz
* Create a Student Directory command line app from scratch
* Rank to 6 kyu on Codewars
* Create GitHub CV

### Evidence

* [First pair-programming: FizzBuzz challenge](https://github.com/maddc0de/fizzbuzz)
* [Student Directory for a Villains Academy](https://github.com/maddc0de/student-directory)
* [codewars profile](https://www.codewars.com/users/maddc0de)
* [Github CV](https://github.com/maddc0de/CV)

### Resources and other information

* [Tuple pair-programming guide](https://tuple.app/pair-programming-guide)
