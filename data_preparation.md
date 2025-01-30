# why do we need to prepare our data?
let's say that we want to write a program that mimics what trna does in real life. 
we want our program to go through a dna sequence and read the sequence three letters by three letters, codon-based, and then translate each to its corresponding amino acid.

before even starting to write the program, we need to tell our programming language which codon corresponds to which amino acid.
for that we would go to [standard genetic code page](https://www.ncbi.nlm.nih.gov/Taxonomy/taxonomyhome.html/index.cgi?chapter=tgencodes#SG1) and see the codon-amino acid pars. 

**we _see_ this table but how can our programming language access it?**

![codon-amino acid](codon_to_amino_acid/1.png)

data preparation here means that you make these types of information readable files for your programming language.
for example, this data in html on a website needs to be converted into a `.csv` (comma-separated) or `.xlsx` (excel) file to make it accessible and compatible for your program.

if you learn how to do this right, the rest of the programming would be easy, especially with all the ai help we have.

# how to prepare your data

i use VS Code as my code editor and i access wsl remotely inside it. 

so let's use the codon - amino acid pair for creating the table.

**1. copy data**

we copy from the website and paste it into a file with `.csv` extension in VS Code.
(you need to create a new file and call it something like `data_preparation.csv` to get a file in csv format.)

![codon amino acid](https://github.com/user-attachments/assets/3572afc1-9ba9-431d-84bf-0ad9df224a03)

**2. clean the data**

we actually don't need all the information here. just the pairs would be enough for us.  
i would like to keep the single-letter amino acid codes and codons and clean everything else.

## before cleaning the data
Always Render Whitespace To See It Visually And Be Able To Count Its Number.

go to your VS Code settings, search for **rendering whitespace**, and set it to `all`. after activation, it should look like this:

![codon amino acid](https://github.com/user-attachments/assets/7631db5d-6f66-4c2c-bd6f-7003112a1a46)

now we can delete all the information that we don't want manually, or we can use a tool called **regular expression** or **regex** for short.

do whichever you feel most comfortable with for your first data preparations, but regex is super easy and fast, so i am using it here.

> also you don't need to memorize any regex patterns. you can always search & ask ai.

- press `ctrl + H` in vs code to access regex:

![codon amino acid](https://github.com/user-attachments/assets/3357ecef-243a-4390-937a-cf27b09f4202)

- then type this on the first line and the latter to the second:

```regex
(\w{3}) (\w) (\w{3})
```
```regex
$1,$2
```

![codon amino acid](https://github.com/user-attachments/assets/b95e5e6f-91ee-4920-8d94-dfb5633c9c87)

- then replace them by pushing enter (or replace all).

![codon amino acid](https://github.com/user-attachments/assets/9276fd15-11eb-4ec1-a23f-26694f1d58a3)

- you can fix the rest manually.

also, pay attention to the tiniest details, like how many spaces are where. they could cause big trouble later. make it as clean and smooth as possible.

![codon amino acid](https://github.com/user-attachments/assets/d5a7d0e1-1507-46e4-aa1c-5370fab33c5a)

- now line them:

```regex
(\w{3}),(\w)
```
```regex
$1,$2\n
```
![codon amino acid](https://github.com/user-attachments/assets/c572c5a2-9b40-4e01-a762-f3e5853e9ddf)


- use `^` followed by six spaces, and leave replace empty:

```regex
^
```
```regex

```

![codon amino acid](https://github.com/user-attachments/assets/045003c4-4a6e-4678-aede-505cd558d137)


- fix the rest manually:

![codon amino acid](https://github.com/user-attachments/assets/b87df334-3e86-4f77-bb9f-cb2cd6b10540)


- delete the space between the lines (replace by nothing):

```regex
^\s*$\n
```
```regex

```

![codon amino acid](https://github.com/user-attachments/assets/c01cf38b-c201-4206-b662-721ce1da0367)


save your file (ctrl + S) and enjoy working with it.

and the answer to our introductory question will be discussed on the dictionaries page.




















