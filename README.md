# FISPEL
A small Esolang i wrote that has a simple syntax and just 12 commands + 6 prefixes.

## How to run FISPEL?
Just download the right release for your OS and use the terminal to run it.

## Actually coding some programs in it
First just create a `.fispel` document. Now just write some code and use the terminal and FISPEL to run it.

### The syntax
```
<prefix> <command> <parameter>
```

### The memory
There are 2 registers that will be named A and B respectively, 3 booleans that will be called C, D, and E respecitely, and an infinite memory "tape".

### The commands
#### `reserve`
It creates a new variable in the tape. At startup the tape starts at a length of 0 variables.

#### `free <slot>`
It deletes the variable with index `<slot>` in the tape and shifts all the following variables one index left.

#### `post <slot>`
It sets the variable with the index `<slot>` in the tape to A.

#### `get <slot>`
It sets A to the variable with the index `<slot>` in the tape.

#### `transfer_main <count>`
It decrementrs A and increments B `<count>` times.

#### `transfer_secondary <count>`
It increments A and decrements B `<count>` times.

#### `output`
It adds A as an ASCII character to the output buffer.

#### `input`
It sets A to a character read from the console.

#### `return`
It prints the output buffer character by character and ends the program.

#### `compare <value>`
Sets C to true if A is equal to `<value>`, sets D to true if A is less than `value`, or sets E to true if A is higher than `value`.

#### `gosub <line>`
Continues running the program at line `<line>` and stores the original line internally.

#### `returnsub`
Gets the internal return line address and goes to that line.

### Prefixes
Prefixes do the command after them if a condition is true.

#### `?`
This prefix will run the following command if C is true.

#### `!?`
This prefix will run the following command if C is false.

#### `<?`
This prefix will run the following command if D is true.

#### `!<?`
This prefix will run the following command if D is false.

#### `>?`
This prefix will run the following command if E is true.

#### `!>?`
This prefix will run the following command if E is false.

**Note: Put a space between the command and the prefix or the interpreter will crash.**
