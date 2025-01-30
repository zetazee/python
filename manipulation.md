# text manipulation

text manipulation in python means making changes to a text. this text can be any type of string; in our case, we are working with dna strings.

i will propose the question, then you think about the steps you need to take to solve the puzzle. once you have a plan, you can untoggle the answers.

let's start.

1.  **write a program that will print GC content of this sequence.**

`dna_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'`

<details>
  <summary>think.</summary>
  <ul>
    <li>count how many times G appears.</li>
    <li>count how many times C appears.</li>
    <li>sum them up.</li>
    <li>divide to the whole length.</li>
  </ul>
</details>  

  do.

  ```python
  dna_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'

  G_content = dna_seq.count('G')
  C_content = dna_seq.count('C')

  content_GC = G_content + C_content

  ratio = content_GC / len(dna_seq)

  print(ratio * 100)
```

2. ** write a program that will print the complement of this sequence.**

`dna2_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'`

<details>
  <summary>think.</summary>
  <ul>
    <li>go through the string and change a to t and save the new string in a variabe. > this won't work becasue will be rewritten every time.</li>
    <li>it should do it in one go. start from the beginning, change a to t and t to a, g to c and c to g.</li>
  </ul>
</details> 

do.

```python
replace_A = dna2_seq.replace('A', 't')
replace_T = replace_A.replace('T', 'a')
replace_G = replace_T.replace('G', 'c')
replace_C = replace_G.replace('C', 'g')

print(replace_C.upper())
```

improve.

```python
dna2_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'

equivalence_dict = {
    'A':'T',
    'T':'A',
    'C':'G',
    'G':'C',
}

complementary_dna = []

for base in dna2_seq:
    replace = equivalence_dict[base]
    # now prevent re-write by writing every replaced character to a new string
    complementary_dna.append(replace)

string = ''

print(string.join(complementary_dna))
```




















