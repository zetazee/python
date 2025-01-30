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
<details>
  <summary>do.</summary>
  
  ```python
  dna_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'

  G_content = dna_seq.count('G')
  C_content = dna_seq.count('C')

  content_GC = G_content + C_content

  ratio = content_GC / len(dna_seq)

  print(ratio * 100)
```
</details>






















