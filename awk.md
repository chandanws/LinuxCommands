# Awk commands

## Common usage
- Text processing
- Generating test report

Awk command starts with BEGIN, then read each line (until EOF) from file or stdin and perform provided rules and last ends with END

Text file **marks.txt** containing following information

| Sr No      |  Name         | Subject  | Marks  |
| ---------- |:-------------:| --------:|--------|


- below command will print each line from marks.txt file.

    **_awk '{print}' marks.txt_**

- below command will print the header, then print all lines from the file and print footer at the end. $0 signifies each line

    **_awk 'BEGIN{printf "Sr No\tName\tSubject\tMarks"} {print $0} END{printf "------Footer------"}' marks.txt_**

- below command will pretty print the awk program in an output file (default file awkprof.out)

    **_awk --profile 'BEGIN{printf "----Header----\n"} {print $0} END{printf "------Footer------\n"}' ''_**

- '-v' option defines a variable 

    **_awk -v name=chandan 'BEGIN{printf "Name: %s\n", name}'_**

- printing columns

    **_awk '{print $2 "," $3}' marks.txt_**

- printing columns if any line is matched with pattern. /h/ is a pattern

    **_awk '/h/ {print $2}' marks.txt_**


