Title： Editing a Little Faster
Date: 2014-10-1
Category: Vim

## Editing a Little Faster
### Additional movement commands
w	move forward a word

b	move backward a word

$	move to the end of line

^	move to the start of line

2w

2b

2$

2^	**did work?**

### Quick searchs along a single line
Searching Along a Single Line

fx	forward searchs the line for the single character x

Fx	backward searcfs the line for the single character x

tx	is different with fx just stop on one character before the indicate character

Tx	is different with Fx just stop on one character before the indicate character

**f just receive a charactor just after f, so 3fx search 3rd x in the line and move to it.But you can't use f3x,cause this will search 3, and remove a character.**
3fx	
3Fx

### Move to a specific line
3G	move to line 3

### Show where am i
Ctrl + G

Some time you will see col "6-8",**This mean the character is character 6,but because of tab,true character is on position 8.**

### Telling where you are in a file
**:set number	**	let vim to show number before each line

### Scrolling Up and Down
Ctrl + U	backword half page

Ctrl + D	forward half page

### Additional delete and change commands
d3w		delete 3 words execute 1 time

2dw		delete 1 words execute	3 times

3d2w	delete	2 words execute 3 times

d$		delete to the end

**d3fx	delete to the third x of the line**

c	means change

cw	delete a word,and insert mode

cc	delete a line, and insert mode

c3fx delete to the 4rd x, insert mode



### The repeat command
**. is the repeat command.It will repeats the last change command like 'd2fx' 'c2fx'**

### Join Lines
J	join two line in to one

### Replace command
5ra		execuate ra 5 times

r5a		will replace current character with 5 and then in append mode

### Change Case
~	change case of the next character

3~	change case of 3 character

### Keyboard macros
q+register	register is character a to z

### Digraphs
Digraphs	used to input character that cant input by keyboard.

**Ctrl + k + digraph**

:digraphs 	show the digraphs of vim

**But can this work on vim? It can be used on MacVim.** 
