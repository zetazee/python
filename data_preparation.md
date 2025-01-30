![3](https://github.com/user-attachments/assets/e24b4913-9a51-428f-ab65-b071b0a3c946)# why do we need to prepare our data?
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

1. copy data
we copy from the website and paste it into a file with `.csv` extension in VS Code.
(you need to create a new file and call it something like `data_preparation.csv` to get a file in csv format.)

![codon amino acid](https://github.com/user-attachments/assets/3572afc1-9ba9-431d-84bf-0ad9df224a03)

2. clean the data
we actually don't need all the information here. just the pairs would be enough for us.  
i would like to keep the single-letter amino acid codes and codons and clean everything else.

## before cleaning the data
Always Render Whitespace To See It Visually And Be Able To Count Its Number.

go to your VS Code settings, search for **rendering whitespace**, and set it to `all`. after activation, it should look like this:

![codon amino acid](https://github.com/user-attachments/assets/7631db5d-6f66-4c2c-bd6f-7003112a1a46)

now we can delete all the information that we don't want manually, or we can use a tool called **regular expression** or **regex** for short.

do whichever you feel most comfortable with for your first data preparations, but regex is super easy and fast, so i am using it here.

press `ctrl + H` in vs code to access regex:

![codon amino acid](https://github.com/user-attachments/assets/3357ecef-243a-4390-937a-cf27b09f4202)




















