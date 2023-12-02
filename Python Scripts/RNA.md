# Transcrição de DNA para RNA em Python

Este documento contém cinco scripts distintos em Python para transcrever uma sequência de DNA em RNA, substituindo todas as ocorrências de 'T' por 'U'.

## Scripts

Abaixo estão as diferentes abordagens implementadas em Python para resolver o problema de transcrição de DNA para RNA.

### Script 1: Substituição direta
```
def transcribe_dna_to_rna_1(dna):
    return dna.replace('T', 'U')
```
### Script 2: Usando expressões regulares
```
import re

def transcribe_dna_to_rna_2(dna):
    return re.sub('T', 'U', dna)
```
### Script 3: Usando list comprehension e join

```
def transcribe_dna_to_rna_3(dna):
    return ''.join(['U' if nucleotide == 'T' else nucleotide for nucleotide in dna])
```

### Script 4: Usando um loop for e construção de string

```
def transcribe_dna_to_rna_4(dna):
    rna = ''
    for nucleotide in dna:
        if nucleotide == 'T':
            rna += 'U'
        else:
            rna += nucleotide
    return rna
```

### Script 5: Usando a função map

```
def transcribe_dna_to_rna_5(dna):
    return ''.join(map(lambda x: 'U' if x == 'T' else x, dna))
```
## Uso

Para utilizar qualquer um dos scripts, carregue primeiro a função desejada no seu ambiente Python. Em seguida, chame a função passando uma sequência de DNA como argumento para obter a sequência de RNA transcrita.
