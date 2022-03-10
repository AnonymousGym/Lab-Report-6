# Lab Report 5

>I first run the bash script in both Joe's version of MarkdownParse and my own MarkdownParse by using the following command:

            time bash script.sh>results.txt

>All the results are stores in results.txt in both folders. I then use the command to compare two results.txt:
            
            diff markdownparse1/results.txt markdownparse2/results.txt

>By doing this, I find two test files that two versions of MarkdownParse show different outputs.

<br>

## First test file: 22.md
>We first have a look at the contents of 22.md and the markdown preview:

<img src = "719B418E-6A1B-4C9D-8E81-952CCE5AA5C2.jpeg">
<img src = "064451E2-B955-44D6-ABB3-0D3BB8A14DB6.jpeg">


>Apparently here, it is counted as a valid link by markdown. The following is the output of Joe's and my own MarkdownParse:


<img src = "D20B3FC7-5C62-4BA0-92C3-BB1434CFA790_4_5005_c.jpeg">
<img src = "4E9BB09D-DBF8-46E7-A94E-C0D0DA61E526_4_5005_c.jpeg">


>My version of MarkdownParse gives the right output, while Joe's gives the wrong output. The reason for this is that in Joe's MarkdownParse, it checks the index of "". It returns the link only if the index of "" is -1. In other words, it returns the output only if there is no "" in the link. Therefore, the following part of code should be fixed to deal with the conditions that the links are valid with "". 

<img src = "C70341D9-A877-4398-B332-7758B500EF76_4_5005_c.jpeg">

<br>

## Second test file: 578.md
>We first have a look at the contents of 578.md and the markdown preview:

<img src = "0BC48934-E8E0-4C93-A0E6-139ADCC13F65_4_5005_c.jpeg">
<img src = "4A28FEA7-252A-48AE-90F3-89D581B76F63_4_5005_c.jpeg">

>Apparently here, it is not counted as a valid link by markdown because there is a ! before brackets. It is counted as a picture. The following is the output of Joe's and my own MarkdownParse:

<img src = "66BF4F82-24E4-4B71-B5F1-1522D41B0D46_4_5005_c.jpeg">
<img src = "C03E799D-31A6-4AE3-BD02-5B57530974F7_4_5005_c.jpeg">

>My version of MarkdownParse gives the wrong output, while Joe's gives the right answer. The reason for this is that in my own MarkdownParse, I didn't check whether there is ! before brackets. Therefore, The following part should be refined so that it can deal with the condition about !.

<img src = "ACDC544D-A8B6-48E1-B0DC-B835854366AB.jpeg">