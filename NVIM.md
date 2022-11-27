# Navigation (use with numbers to jump) for development mode
# Mix copy(y), undo, redo, commenting etc alomost everything can be combined with numbers


## j - down
## k - up
## l -right
## h - left

## % for jumping between two parenthesis

## x - cut a letter
## r - replace a letter
## R - replacing through the whole line

## i - insert (to the left of the letter)
## I - insert (to the begninng of the line)
## a - insert (to the right of the letter)
## A - insert (to the last of the line)
## o - jump to the new line below
## O - jump to the new line above
## v - visual mode
## w - to the next word
## b - before the word
## e - last of the  word

## W - to the next word (without considering the word)
## B - to the before word (without considering the word)
## y - copy
## p - paste
## D - delete from the letter to the last of the line
## dw - delete a word (u can use with numbers too like 2dw 0r d2w)
## db - delete a word before ( u can use with numbers too like d2b or 2db)
## diw - delete in a word (u can use number too)
## ciw - change + insertion in a sentence

# Quotion can be replced with anything(any symbol-between)
## di" - in a quotaion mark (deletion)
## yi" - in a quotation or any mark (copy)
## ci" - cut plus insertion in a quotaion mark (in a quotation)

## C - delete + insertion from the letter to the last of the line 
## cc - insertion from the start of the line and deleting the rest
## 0 - begining of the line  (as a movement)
## $ - last of the line (as a movement)
## d0 - deletion from the word to the start (as a movement) 
## d$ - deletion from the word to the end ("")
## de - deletion of a word to the last ("")
## yiw - copying a word

# in visual mode

## y - copy by selecting text
## P - pasting before the letter
## p - pasting after the letter


## t(any letter or symbol) - to jump before the specific letter or symbol (till)
## f(any letter or symbol - to jump on the letter
## yt(any letter or symbol)/ dt(till any l)/ct(any letter) , 
## yf(any letter or symbol)/ df(any l)/cf(any letter) , 
## T - opposite in opposite direction of the line
## f - opposite in opposite direction of the line

# jumping
## gg - jump to the first line
## jumping to the line :number of the line
## shift + g - last 
## / - to search anything 
## n to jump to the next word
## N to go the back word
## # to up find
## * to down found
## m+any letter to mark a line
## '(any letter u used in mark) - to come to that line

# intending a line
## << - left intend
## >> - right intend
## capital(V + j/k) - to select lines
## (ctrl + v) - visual block then  + j/k to delete by column wise
## == - to automatic indent
## V + j/k and then = - autoindent so many lines
## gg=G - to auto indent the whole file
### gg - start
### g - end

## zz - to center the line in the between of screen

# search and replace
## :%s/replaceablenamegoeshere/replacewithgoeshere (for full file)
## s/replaceablenamegoeshere/replacewithgoeshere (for selected text)
## dd - delete a line and then . to delete the consecutive lines

## . executes the last command u applied (can be used with dt(anyletter) or ct(anyletter))

## :reg - registered history
## selecting every thing - V + G

