Quick note on solving Wordle using shell script:
- download list of common words into your directory
- sort it to make sure
- grep '.....' select words matching a particular pattern i.e. grep '...er' will produce 'wider' 'older' etc...
- grep -v -e 'c' etc... will eliminate words containing those characters
- grep 't' will select only words that contain 't' located anywhere.  This is the case when we found 't' in the word but we haven't found its location.
- finally sort it to ensure no duplicates if there is
<blockquote>grep -o -w '\w\{5,5\}' common-words.txt | sort | uniq |grep '...e.' |grep -v -e 'c' -e 'm' -e 'p' -e 'l' -e 's' -e 'a' -e 'r' -e 'h' |grep 'e' | grep 't' | grep 'o'|sort | uniq </blockquote>
