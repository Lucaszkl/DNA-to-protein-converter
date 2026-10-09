# DNA-to-protein-converter
simple DNA to mRNA to protein script

 codon_table = {
...     # Alanine (A)
...     'GCA':'A', 'GCC':'A', 'GCG':'A', 'GCU':'A',
...     # Arginine (R)
...     'AGA':'R', 'AGG':'R', 'CGA':'R', 'CGC':'R', 'CGG':'R', 'CGU':'R',
...     # Asparagine (N)
...     'AAC':'N', 'AAU':'N',
...     # Aspartic acid (D)
...     'GAC':'D', 'GAU':'D',
...     # Cysteine (C)
...     'UGC':'C', 'UGU':'C',
...     # Glutamic acid (E)
...     'GAA':'E', 'GAG':'E',
...     # Glutamine (Q)
...     'CAA':'Q', 'CAG':'Q',
...     # Glycine (G)
...     'GGA':'G', 'GGC':'G', 'GGG':'G', 'GUG':'G',
...     # Histidine (H)
...     'CAC':'H', 'CAU':'H',
...     # Isoleucine (I)
...     'AUA':'I', 'AUC':'I', 'AUU':'I',
...     # Leucine (L)
...     'CUA':'L', 'CUC':'L', 'CUG':'L', 'CUU':'L', 'UUA':'L', 'UUG':'L',
...     # Lysine (K)
...     'AAA':'K', 'AAG':'K',
...     # Methionine (M) - Start Codon
...     'AUG':'M',
...     # Phenylalanine (F)
...     'UUC':'F', 'UUU':'F',
...     # Proline (P)
...     'CCA':'P', 'CCC':'P', 'CCG':'P', 'CCU':'P',
...     # Serine (S)
...     'AGC':'S', 'AGU':'S', 'UCA':'S', 'UCC':'S', 'UCG':'S', 'UCU':'S',
...     # Threonine (T)
...     'ACA':'T', 'ACC':'T', 'ACG':'T', 'ACU':'T',
...     # Tryptophan (W)
...     'UGG':'W',
...     # Tyrosine (Y)
...     'UAC':'Y', 'UAU':'Y',
...     # Valine (V)
...     'GUA':'V', 'GUC':'V', 'GUG':'V', 'GUU':'V',
...     # STOP Codons
...     'UAA':'X', 'UAG':'X', 'UGA':'X'
... }
...
... dna_sequence = "ATGCTCGATCAGAGCAGTTAGAGATAGAGACCGCCAGAC" (ADD ANY DNA SEQUENCE (ATGC))
... mrna_sequence = dna_sequence.replace("T", "U")
...
... print(f"DNA:  {dna_sequence}")
... print(f"mRNA: {mrna_sequence}")
...
... protein = []
...
... for i in range(0, len(mrna_sequence), 3):
...     codon = mrna_sequence[i:i+3]
...
...     if len(codon) < 3:
...         break
...
...
...     amino_acid = codon_table.get(codon, '?')
...
...     if amino_acid == 'X':
...         break
...
...     protein.append(amino_acid)
...
...
... protein_string = "".join(protein)
... print("Resulting Protein:", protein_string)
