
# Contador de Nucleotídeos em Python

Este documento contém cinco scripts distintos em Python para contar as ocorrências dos nucleotídeos A, C, G e T em uma sequência de DNA.

## Scripts

Abaixo estão as diferentes abordagens implementadas em Python para resolver o problema de contar nucleotídeos em uma cadeia de DNA.

### Script 1: Usando a classe Counter do módulo collections

```python
from collections import Counter

def count_nucleotides_1(dna):
    counts = Counter(dna)
    return counts['A'], counts['C'], counts['G'], counts['T']
```

### Script 2: Usando um dicionário e um loop for

```python
def count_nucleotides_2(dna):
    counts = {'A': 0, 'C': 0, 'G': 0, 'T': 0}
    for nucleotide in dna:
        counts[nucleotide] += 1
    return counts['A'], counts['C'], counts['G'], counts['T']
```

### Script 3: Usando compreensão de lista

```python
def count_nucleotides_3(dna):
    return (dna.count('A'), dna.count('C'), dna.count('G'), dna.count('T'))
```

### Script 4: Usando um loop manual e incrementação

```python
def count_nucleotides_4(dna):
    a, c, g, t = 0, 0, 0, 0
    for nucleotide in dna:
        if nucleotide == 'A': a += 1
        elif nucleotide == 'C': c += 1
        elif nucleotide == 'G': g += 1
        elif nucleotide == 'T': t += 1
    return a, c, g, t
```

### Script 5: Usando map e funções lambda

```python
def count_nucleotides_5(dna):
    return tuple(map(lambda x: dna.count(x), 'ACGT'))
```


## Uso

Para utilizar qualquer um dos scripts, carregue primeiro a função desejada no seu ambiente Python. Em seguida, chame a função passando uma sequência de DNA como argumento para obter a contagem de cada nucleotídeo.
