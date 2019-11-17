# Binary Patching

The original assignment webpage put up by my professor is "quiz 0x01 - CS6332-F2019 @ UTD.html", along with the related files folder.
The original files we worked on are crackme0x00, crackme0x01, and crackme0x02. The download links in the original webpage link to modified files created for later assignments.

I used radare2 to analyze the exectuables and edit the assembly. I opened them in writable mode using the -w flag, "r2 -w crackme0x0-".

# Part 2
For part 2, my secret number is 53108.

For crackme0x00, the secret is a string, "250382", which r2 showed was located at address 0x804858f. Using "s 0x0804858f" to seek to that location, I replaced the assembly located there by pressing 'A' to enter edit mode and typing: .string "53108"

For crackme0x01, the secret is a hexadecimal number, 0x149a, which is 5274 in decimal. To change this to my secret number, which is 0xcf74 in hex, I entered edit mode at the particular line of code where the comparison takes place (address 0x0804842b) and typed: cmp dword [local_4h], 0xcf74

# Part 3
To change the execution of the program, I replaced existing lines of assembly with NOPs as necessary to make program print "Password OK" no matter the input, getting rid of the branching statement and any code related to the "Incorrect password" output.

<!-- Future plan: add pictures! -->