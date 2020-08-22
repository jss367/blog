vim notes

hjkl to move around

u - undo

w - start of next word
e - end of the word
b - beginning of the word

3w - move 3 words

3igo - write the word "go" three times


To find a word in Vi/Vim, simply type the / or ? key

fo - find next "o"


3fq - find third instance of "q"

% - jump from a { to a } or ( to a )

0 - beginning of line
% - end of line
* - find the next instance of the word under the cursor
# - find the previous instance of the word under the cursor

2G - go to line 2

searching for text:
/
n - next
N - previous

O - insert new line above
o - insert new line below


x - delete character under cursor
X - delete character to the left of cursor

r - replace single character without switching to insert mode

d - delete
dw - delete first word on right side of cursor
p - print the deleted word

d2e - delete two words?
. - keep deleting

v - visual mode

show line numbers - set number (or set nu for short)
or, to do it by default: Add set number to your .vimrc file in your home directory.


set breakpoint: 158 b

Explore - lets you look at other files; navigate the file structure



ls to see multiple files open in vim

copy and paste:
yy to yank one line
p to paste


replace a section
First, you'll need to change your username
:%s/jsimonelli/yourusernamehere/g

Then, your folder path

If you're in data ops, it would be
:%s/orig_path1\/orig_path2\/orig_path3/new_path1\/new_path1/g

If you're in computer vision, it would be
:%s/orig_word/new_word/g

Substitute:
g means global (change every case, not just the first)
% means all lines

:%s/username/[NAME]/g