Date: 2014-9-29
Title: Learning Perl-Scalar Data
Category: Learning Perl

## Scalar Data
### Numbers
**All numbers are same format internally.They are treated as double precision floating-point values.**

#### Floating-Point Literals
1.25

25.0000

-6.5e24

+34.01e12

#### Integer Literals
0

2014

-2551

#### Non-Decimal Interger Literals
base 2: 0b1110

base 8: 0377

base 16: 0xab

#### Numeric Operators
addition,subtraction,multiplication, and division operators

**but modulus operator is different.It will first reduce both operants to integer values.so 10.5%2.3 is computed as 10%3.**

**power operator is writen as two asterisk. 2\*\*3 **

### String
Typical strings are printable sequence of letters, digits, and punctuation in the ASCII 32 to ASCII 126 rangge.
**However perl has the ability to have any character in a string, so it means that you can create, scan, and manipulate raw binary data as strings and that is something with which many other utilies would have freate difficulty.**

For example:
	1. you can update an image by load it in string
	2. you can update an complied program by load it in string
	
#### Single-Quoted String Literals
Any charactor other than a single quote or a backslash is between quote mark stands for itself inside a string.
Example:
**\n is not a newline,but two character \ and n**
'hello
world'
**backslash is escape just before single quote or backslash**

#### Double-Quoted String
Double quoted string is as common as other language.


\l lowercase the next letter

\L lowercase the following letters until \E

\u uppercase the next letter

\U uppercase the following letters until \E

**\Q quote non-word character by adding a backslash until \E**

\E end of \l \L \u \U \Q

\cC Ctrl + C

**\007 ASCII value 7 (base 8)**

**\0x7f ASCII value (base 16)**

\n newline

\r return

\r tab

##### variable interpolated
vaiable name in double-quoted string will replaced by their data.Just like bash.


#### String operator
concatenated with . operator
repetition: consisting of the single lowercase letter x.
example:
	"fred" x 3
	 "barney" x 4
**The copy count is just truncated to integer value.A copy count less than one result in empty**
	 
#### Automatic conversion between numbers and strings
Perl will automatic converts between numbers and strings as needed.
It all counts on what the operator need.
For Example:
"z" . 3 * 7 	"z21"
"12fred34" * 3  36

#### Choosing Good Variable Name
Similarly, properly placed underscores can make a name easier to read and understandm especially if your maintenance programmer has a different spoken language backgroud than you have.

#### Scalar Assignment & Binary Assignment Operators
Nearlly all binary operator has a related binary assignment operator.
For example:
	$fred = $fred + 5;
	$fred += 5;
	
	$barney = $barney * 3;
	$barney *= 3;
	
	$str = $str . " ";
	$str  .= " ";
	
#### 	Output with print
The print() operator make output possible.
It take scalar argument and puts it without andy embellishment onto standard output.

print "The answer is ", 6 * 7;


#### interpolation of Scalar Variable into Strings
**When using doube quoted mark. Any scalar variable name in the string is replaced with its current value.**

But interpolation is nothing with single quote.

**The variable name will be the longest possible variable name that makes sences at part of string.This may not be what you want if u just want to append sth just follow the replaed value immediately.**

$what = "apple;
$n = 3;
print "fred ate $n $whats"; //perl will think $whats is the variable name
print "fred ate $n ${what} s"	//proper behavior

${ }point out what vaiable is


####  Operator precedence and associativiy
So should you just remember the precedence chart? No! Nobody does that.Instead use parenthese when you don't remember the order of operation or when you are two busy to look in the chart.


#### Comparison Operators


| Comparison | Numeric | String |
|----|----|----|
| Equal | == | eq |
| Not equal | != | ne |
| Less than | < | lt |
| Greater than | > | gt |
| Less than or equal to | <= | le |
| Greater than or equal to | >= | ge |


#### Boolean Values

- If the value is a number, 0 means false,others mean true
- If the value is string, the empty string('') means false, all others mean true
**Because the string '0' is the same scalar value as the number 0, Perl has to treat them same.That means '0' is the only nonempty string that is false.**


#### Get User Input
Each time  you use <STDIN> in a place where a scalar value is expected, Perl reads the next complete text line from standard input and use that string as the value of <STDIN>

$line = <STDIN>
if ($line eq "\n") {
	print "That was just a blank line!\n";
} else {
	print "That line of input was: $line";
}

**<STDIN> typically has a newline character on the end of it.**


#### The chomp operator
It works on a vaiable, and the variable has to hold a string.If the string ends in a newline character, chomp can get rid of newline.

	chomp($text = <STDIN> )	;
		
	$text = <STDIN>;
	chomp($text);
	
**chomp is a function,as a function, it has a return value.The return value is the character being removed.**
**If a string is end with more than one new lines.chmop just remove one newline.**



#### The While Control Structure 
	$count = 0
	while ($count < 10) {
		$count += 2;
		print("count is now $count\n");
	}
**The block curly braces are required.**
#### The if Structure
**The block curly braces are requied.(Not same as C)**


#### The undef Value 
If u use an variable before you give it an value.It will act as zero for number, and as empty string.**But undef it is not an number or a string.**

#### The defined Function
**One operator can return undef is line-input <STDIN>, use defined() function can tell if the variable is undef or is just an empty string.If variable is undef it return false, and another else it return true.**
$madonna = <STDIN>
if(defined($madonna)){
	print("The input was $madonna");
} else {
	print("No input available!\n");
}




