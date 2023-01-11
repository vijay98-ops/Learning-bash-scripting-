# first_cmd out is input for second_cmd and second_cmd error is redirected to stderr.txt
$echo bijayp | ./script.sh 2> stderr.txt
$echo bijayp | ./script.sh 2> stderr.txt > stdout.txt

# takes input from name.txt and redirects error to stderr.txt
$./script.sh < name.txt 2> stderr.txt

# working with text files
$ wc kitty_ipsum_1.txt # gives count of lines, words and bytes of file
$ wc -l kitty_ipsum_1.txt # counting number of lines

## using pipe to give input to wc command
$ cat kitty_ipsum_1.txt | wc -l
$ cat kitty_ipsum_1.txt | wc -l >> kitty_info.txt # appending lines count to kitty_info.txt file
$ wc -m < kitty_ipsum_1.txt >> kitty_info.txt # using redirection instead of pipe

## using grep to match pattern in a text file
$ grep 'meow' kitty_ipsum_1.txt
$ grep --color 'meow' kitty_ipsum_1.txt
$ grep --color -n 'meow' kitty_ipsum_1.txt # -n flag for line numbers
$ grep --color -n 'meow[a-z]*' kitty_ipsum_1.txt # the pattern is for words that start with meow (e.g., meows)
$ grep -c 'meow[a-z]*' kitty_ipsum_1.txt # gives the count of lines where the pattern appears
$ grep -o 'meow[a-z]*' kitty_ipsum_1.txt # gives words only
$ grep -o 'meow[a-z]*' kitty_ipsum_1.txt | wc -l # count of words
$ grep -n pattern textfile # to get the line numbers
$ grep -E 'dog_words|woof_words' # search for two patterns, -E flag is for extended regular expressions to recognise |

## replacing texts
$ sed 's/<pattern_to_replace>/<text_to_replace_with>/' filename
$ sed 's/<pattern_to_replace>/<text_to_replace_with>/i' filename # for casing in letters. A a
## also use g for global inplace of i for replacing all instances of pattern
$ sed 's/<pattern_to_replace>/<text_to_replace_with>/' < filename
$ cat filename | sed 's/<pattern_to_replace>/<text_to_replace_with>/'

## sed and grep
$ grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/[0-9]+/1/' # replace two digit numbers

### match everything else on each line and replace with captured numbers
$ grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/' # we get only line numbers
$ grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/' >> kitty_info.txt

## difference between two files
$ diff file1 file2
$ diff --color file1 file2



