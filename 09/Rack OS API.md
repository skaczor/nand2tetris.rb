# The Rack OS API #

The Rack language comes with a collection of seven built-in classes that extend the language's capabilities. This standard library, which can also be viewed as a basic operating system, includes the following classes, all implemented in Rack:


## Math ##


This class enables various mathematical operations.

### Class Methods ###

#### `abs(x)` ####

Returns the absolute value of x.

#### `multiply(x, y)` ####

Returns the product of x and y.

#### `divide(x, y)` ####

Returns the integer part of x/y.

#### `min(x, y)` ####

Returns the minimum of x and y.

#### `max(x, y)` ####

Returns the maximum of x and y.

#### `sqrt(x)` ####

Returns the integer part of the square root of x.


## String ##


This class implements the String data type and various string-related operations.

Compatibility Note: This class has instance methods that are not compatible with the built-in implementation of the nand2tetris Virtual Machine. For that reason, if your program uses any instance methods of the String class, you should include the String class implementation it in the folder where your program resides.

### Class Methods ###

#### `new(maxLength)` ####

Constructs a new empty string (of length zero) that can contain at most maxLength characters.

#### `backSpace()` ####

Returns the backspace character.

#### `doubleQuote()` ####

Returns the double quote (“) character.

#### `newLine()` ####

Returns the newline character.

### Instance Methods ###

#### `dispose()` ####

Disposes this string.

#### `length()` ####

Returns the length of this string.

#### `charAt(j)` ####

Returns the character at location j of this string.

#### `setCharAt(j,` c) ####

Sets the j-th element of this string to c.

#### `appendChar(c)` ####

Appends c to this string and returns this string.

#### `eraseLastChar()` ####

Erases the last character from this string.

#### `intValue()` ####

Returns the integer value of this string (or the string prefix until a non-digit character is detected).

#### `setInt(j)` ####

Sets this string to hold a representation of j.


## Array ##


This class enables the construction and disposal of arrays.

Compatibility Note: This class is not compatible with the built-in implementation of the nand2tetris Virtual Machine. Due to its widespread use in almost any program, this class should be implemented directly in the compiler, rather than invoking an external Array class.

### Class Methods ###

#### `new(size)` ####

Constructs a new array of the given size.

#### `dispose()` ####

Disposes this array.


## Output ##


This class allows writing text on the screen.

### Class Methods ###

#### `moveCursor(i,` j) ####

Moves the cursor to the j-th column of the i-th row, and erases the character displayed there.

#### `printChar(c)` ####

Prints c at the cursor location and advances the cursor one column forward.

#### `printString(s)` ####

Prints s starting at the cursor location and advances the cursor appropriately.

#### `printInt(i)` ####

Prints i starting at the cursor location and advances the cursor appropriately.

#### `println()` ####

Advances the cursor to the beginning of the next line.

#### `backSpace()` ####

Moves the cursor one column back.


## Screen ##


This class allows drawing graphics on the screen. Column indices start at 0 and are left-to-right. Row indices start at 0 and are top-to-bottom. The screen size is hardware-dependant (in the Hack platform: 256 rows by 512 columns).

#### `clearScreen()` ####

Erases the entire screen.

#### `setColor(boolean` b) ####

Sets a color (white=false, black=true) to be used for all further drawXXX commands.

#### `drawPixel(x,` y) ####

Draws the (x,y) pixel.

#### `drawLine(x1,` y1, x2, y2) ####

Draws a line from pixel (x1,y1) to pixel (x2,y2).

#### `drawRectangle(x1,` y1, x2, y2) ####

Draws a filled rectangle whose top left corner is (x1, y1) and bottom right corner is (x2,y2).

#### `drawCircle(x,` y, r) ####

Draws a filled circle of radius r<=181 around (x,y).


## Keyboard ##


This class allows reading inputs from a standard keyboard.

### Class Methods ###

#### `keyPressed()` ####

Returns the character of the currently pressed key on the keyboard; if no key is currently pressed, returns 0.

#### `readChar()` ####

Waits until a key is pressed on the keyboard and released, then echoes the key to the screen and returns the character of the pressed key.

#### `readLine(message)` ####

Prints the message on the screen, reads the line (text until a newline character is detected) from the keyboard, echoes the line to the screen, and returns its value. This function also handles user backspaces.

#### `readInt(message)` ####

Prints the message on the screen, reads the line (text until a newline character is detected) from the keyboard, echoes the line to the screen, and returns its integer value (until the first non-digit character in the line is detected). This function also handles user backspaces.


## Memory ##


This class allows direct access to the main memory of the host platform.

### Class Methods ###

#### `peek(address)` ####

Returns the value of the main memory at this address.

#### `poke(address,` value) ####

Sets the contents of the main memory at this address to value.

#### `alloc(size)` ####

Finds and allocates from the heap a memory block of the specified size and returns a reference to its base address. function void deAlloc(Array o): De-allocates the given object and frees its memory space.


## Sys ##


This class supports some execution-related services.

### Class Methods ###

#### `halt()` ####

Halts the program execution.

#### `error(errorCode)` ####

Prints the error code on the screen and halts.

#### `wait(duration)` ####

Waits approximately duration milliseconds and returns.
