# text manipulation

text manipulation in python means making changes to a text. this text can be any type of string; in our case, we are working with dna strings.

i will propose the question, then you take the time to understand what you are being asked and then think about the steps you need to take to solve the puzzle. once you have a plan, you can untoggle the answers. 

give yourself time limit on the `do.` part. you are learning how to use this tool and to do that you need to see a variety of solutions other people have come up with before finding your own way. train your brain with as much as question-answers you can. i didn't do this when i started and now i think i should have spent less time thinking deeply about this small set of questions and more time spreading my sources widely. it's okay, i did that and now i know this. next time different approach.

let's start.

1. **write a program that will print GC content of this sequence.**

dna_seq = `ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT`

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

  <pre><code class="language-python">
dna_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'
G_content = dna_seq.count('G')
C_content = dna_seq.count('C')
    
content_GC = G_content + C_content

ratio = content_GC / len(dna_seq)
print(ratio * 100)
  </code></pre>

</details>

----
2. **write a program that will print the complement of this sequence.**

`dna2_seq = 'ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT'`

<details>
  <summary>think.</summary>
  <ul>
    <li>go through the string and change a to t and save the new string in a variable. > this won't work because it will be rewritten every time.</li>
    <li>it should do it in one go. start from the beginning, change a to t and t to a, g to c and c to g.</li>
    <li>or you can avoid re-write by storing altered character in a new string and adding up to it.</li>
  </ul>
</details>

<details>
  <summary>do.</summary>

  <pre><code class="language-python">
replace_A = dna2_seq.replace('A', 't')
replace_T = replace_A.replace('T', 'a')
replace_G = replace_T.replace('G', 'c')
replace_C = replace_G.replace('C', 'g')

print(replace_C.upper())
  </code></pre>

</details>

<details>
  <summary>improve.</summary>
  <pre><code class="language-python">
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
    # now prevent re-write by writing every replaced character to a new string.
    complementary_dna.append(replace)
    
string = ''
print(string.join(complementary_dna))
  </code></pre>
</details>

----
3. **the motif G*AATTC is the recognition site for the EcoRI restriction enzyme.**

- **PART 1: write a program which will calculate the size of the two fragments that will be produced when the dna seq is digested with EcoRI.**
  
`dna3_seq = 'ACTGATCGATTACGTATAGTAGAATTCTATCATACATATATATCGATGCGTTCAT`

<details>
  <summary>think.</summary>
  <ul>
    <li>find motif position(index).</li>
    <li>simulate the cut.</li>
    <li>calculate len of right and left</li>
  </ul>
  
</details>

<details>
  
  <summary>do.</summary>
  <pre><code>
    dna3_seq = 'ACTGATCGATTACGTATAGTAGAATTCTATCATACATATATATCGATGCGTTCAT'
    cut_index = dna3_seq.find('GAATTC')
    # find will find the exact substring & will return the index of the first occurance.
    # this is also the cut index.
    print(cut_index)
    fragment_1 = dna3_seq[:22]
    fragment_2 = dna3_seq[22:]
    print(fragment_1)
    print(len(fragment_1))
    print(fragment_2)
    print(len(fragment_2))
  </code></pre>
  
</details>

- **PART 2: calculate what part of the dna is coding.**
> here we will assume that any part in uppercase is coding. (you don't need to find start and stop codons for now.)

<details>
  <summary>think.</summary>
  <ul>
    <li>we have two fragments after the cut. all uppercase.</li>
  </ul>
</details>

<details>
  
  <summary>do.</summary>
  <pre><code>
    dna3_seq = 'ACTGATCGATTACGTATAGTAGAATTCTATCATACATATATATCGATGCGTTCAT'
    cut = dna3_seq.find('GAATTC')
    frag_1 = dna3_seq[:cut+1]
    frag_2 = dna3_seq[cut+1:]
    print(len(frag_1))
    print(len(frag_2))
  </code></pre>
  
</details>

----
4. **print this sequence as a list of codons.**

`dna_pf_seq = "ATGACCATCGAAAAGGTCGTTCGTGTTCTGCTTCTGATGGTGCTGGGCGCTGGCCGTACCGTTCGCCGATCTGCTGGTCTTCGTTGCTGAACAGCCTGGCCGCTGGCTTTGAGCTGTTCATGGTGATGACCTGAACGTTCGCTGCTGCTGGCTACTGCTGCTGATGTGCTGAATAA"`

<details>
  
  <summary>think.</summary>
  <ul>
    <li>go through the sequence and read it by three characters.</li>
  </ul>
  
</details>

<details>
  
  <summary>do.</summary>
  <pre><code>
    for index in range(0,len(dna_pf_seq),3):
    codon = dna_pf_seq[index:index+3]
    print(codon)
  </code></pre>
  
</details>

<details>
  
  <summary>improve.</summary>
  <pre><code>
    for index in range(0,len(dna_pf_seq),3):
    codon = dna_pf_seq[index:index+3]
    if len(codon) == 3:
        print(codon)
  </code></pre>
  
</details>

----
5. **calculate what part of this _Prosthecobacter fusiformis_ dna sequence is coding.**

`dna_pf_seq = "ATGACCATCGAAAAGGTCGTTCGTGTTCTGCTTCTGATGGTGCTGGGCGCTGGCCGTACCGTTCGCCGATCTGCTGGTCTTCGTTGCTGAACAGCCTGGCCGCTGGCTTTGAGCTGTTCATGGTGATGACCTGAACGTTCGCTGCTGCTGGCTACTGCTGCTGATGTGCTGAATAA"`

> find regions between start and end codons.

<details>
  <summary>think.</summary>
  <ul>
    <li>go through the dna, read in three base format, find start codon and then stop codon, print it,</li>
    <li>before that, what is codon? DEFINE `codon` for the program.</li>
    <li>move to the next start codon and end codon, print the index and fragment it.</li>
  </ul>
</details>

<details>
  <summary>do.</summary>

  <pre><code>
    dna_pf_seq = "ATGACCATCGAAAAGGTCGTTCGTGTTCTGCTTCTGATGGTGCTGGGCGCTGGCCGTACCGTTCGCCGATCTGCTGGTCTTCGTTGCTGAACAGCCTGGCCGCTGGCTTTGAGCTGTTCATGGTGATGACCTGAACGTTCGCTGCTGCTGGCTACTGCTGCTGATGTGCTGAATAA"
    start = 'ATG'
    end = ['TAG','TGA','TAA']
    for index in range(0,len(dna_pf_seq),3):
        codon = dna_pf_seq[index:index+3]
        if codon == start:
            print(f'there is a start codon in {index} position')
    for index in range(0,len(dna_pf_seq),3):
        codon = dna_pf_seq[index:index+3]
        for item in end:
            if codon == item:
                print(f'there is a stop codon in {index}')
    print(dna_pf_seq[0:90])
    # there is no tRNA for stop codons so we should actually print zero to 86 (which we need to +1 for the end of slicing).
    print(dna_pf_seq[0:87])
  </code></pre>

</details>

































