![Image](img/BannerPowerShell.jpg)

(Photo pixabay.com)

Automation with PowerShell
========================

Recurring tasks on the computer can be conveniently automated via shell script. You can choose from Bourne Shell (bsh), Bourne Again Shell (bash), C Shell (csh), Korn Shell (ksh), PowerShell and many more. But only PowerShell is available as an open source project cross-platform for Linux, macOS and Windows under the MIT license.. 

... ![Image](img/MF.png) *By Markus Fleschutz* 🕑 *January 11, 2019*

The command line
----------------------

To try out PowerShell you need a text console. For this purpose, the convenient Windows Terminal (available for free in the Windows App Store) . 

PowerShell offers the following commands, among others

 cat filename - prints the contents of the specified file.
 cd folder- changes to the specified folder
 cd .. - changes one folder level higher
 clear - clears the display in console window
 cp source filename destination filename - copies the specified file
 date - displays the system time of the computer
 diff filename1 filename2 - shows the difference of both files
 echo text - prints the specified text
 echo $Variable - outputs the content of the given variable
 exit - exits the PowerShell console or the PowerShell script
 help - displays help for PowerShell cmdlets and concepts (very helpful !!!)
 history - shows the commands entered so far
 hostname - prints the name of the computer
 kill process ID - kills the specified process
 ls - lists the contents of a file folder
 mkdir folder name - creates a folder with the specified name
 mv source filename destination filename - moves the specified file
 ping hostnameIP address - checks if the specified computer is reachable on the network
 ps - lists all currently running processes
 pwd - prints the current file path
 rm filename - deletes the specified file or folder (!)
 set variable name value - sets the given variable to the given value
 sleep seconds - waits the specified number of seconds
 wget URL - downloads the specified file from the Internet

## cmdlets

The above commands are actually aliases to so-called cmdlets.  Cmdlets always consist of a verb, a hyphen and a noun, for example `Get-ChildItem` (show file folder). You can use `Get-Command` and `Show-Command` to search for and find cmdlets. Which cmdlets are available depends not only on the PowerShell version used, but also on the operating system and the additional software equipment installed. Cmdlets are basically located in modules.

Writing PowerShell scripts
--------------------------------

Using any text editor, create a new file named `HelloWorld.ps1` with the following content

```
echo Hello World!
sleep 10
```

Then save the file and select Run with PowerShell with a right click. The script will be executed.

## PowerShell features

PowerShell is powerful! PowerShell's capabilities almost approach a programming language. And the examples below work both in a PowerShell script and in the PowerShell console. So just try them out!

### Example 1 Variables & Numbers

```
$PI = 3.1415927
echo $PI
```

### Example 2 Variables & text

```
$var = Hello 
$var += John
echo $var
```

### Example 3 Variables & Text Arrays

```
$days = Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday
foreach($day in $days) {
	echo $day
}
```

### Example 4 Initialize multiple variables

```
$a = $b = $c = 1
echo $a, $b, $c
```

```
$a, $b, $c = 1, 2, 3
echo $a, $b, $c
```

### Example 5 Variables & program output

```
$output = ls
echo $output
```

### Example 6 for loops

```
for($i = 0; $i -le 100; $i++) {
	echo Hello
}
```

### Example 7 foreach loops

```
$colors = red, green, blue
foreach($color in $colors) {
	echo $color
}
```

### Example 8 do-while loops

```
do {
	echo Hello
} while ($false)
```

### Example 9 while loops

```
while ($true) {
    echo Hello
    break
}
```

### Example 10 Infinite loops

```
while ($true) {
	echo ENDLESS
}
```

### Example 11 Comments

```
# comment
1 + 1 # should make 2
```

### Example 12 Comparison operators

```
1 -eq 1 # is equal
0 -ne 1 # is not equal
0 -lt 1 # is less than
0 -le 1 # is less than or equal to
1 -gt 0 # is greater than
1 -ge 0 # is greater than or equal to
PowerShell -like Pow # comparison with wildcards (opposite -notlike)
Jan, Feb, March -contains Feb # comparison with arrays (opposite -notcontains)

```