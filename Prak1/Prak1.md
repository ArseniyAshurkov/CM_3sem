# Практическое занятие №1. Введение, основы работы в командной строке
### Задание 1
 grep '.*' /etc/passwd | cut -d: -f1 | sort

### Задание 2
awk '{print $2, $1}' /etc/protocols | sort -nr | head -n 5

### Задание 3
#!/bin/bash
text=$*
length=${#text}

for i in $(seq 1 $((length + 2))); do
    line+="-"
done

echo "+${line}+"
echo "| ${text} |"
echo "+${line}+"

### Задание 4
#!/bin/bash

file="$1"

id=$(grep -o -E '\b[a-zA-Z]*\b' "$file" | sort -u)

### Задание 5
#!/bin/bash

file=$1

chmod 755 "./$file"

sudo cp "$file" /usr/local/bin/