# Encontrando o Complemento Reverso de uma Sequência de DNA em Python

Este documento contém cinco scripts distintos em Python para encontrar o complemento reverso de uma sequência de DNA.

## Scripts

### Script 1: Uso de dicionário para mapeamento de complementos e reversão de string
```
def reverse_complement_1(dna):
    complement = {'A': 'T', 'T': 'A', 'C': 'G', 'G': 'C'}
    return ''.join(complement[nuc] for nuc in reversed(dna))
```

### Script 2: Uso de str.translate para mapeamento de complementos e reversão de string
```
def reverse_complement_2(dna):
    complement = str.maketrans('ATCG', 'TAGC')
    return dna.translate(complement)[::-1]
```
### Script 3: Uso de expressão regular para substituição e reversão de string
```
import re
def reverse_complement_3(dna):
    complement = {'A': 'T', 'T': 'A', 'C': 'G', 'G': 'C'}
    return re.sub('.', lambda x: complement[x.group()], dna[::-1])
```
### Script 4: Uso de loop e adição de caracteres para construção de complemento reverso
```
def reverse_complement_4(dna):
    complement = {'A': 'T', 'T': 'A', 'C': 'G', 'G': 'C'}
    reverse_complement = ''
    for nuc in reversed(dna):
        reverse_complement += complement[nuc]
    return reverse_complement
```
### Script 5: Uso de função lambda e map para mapeamento de complementos e reversão de string
```
def reverse_complement_5(dna):
    complement = {'A': 'T', 'T': 'A', 'C': 'G', 'G': 'C'}
    return ''.join(map(lambda nuc: complement[nuc], reversed(dna)))
```
## Uso

Para utilizar qualquer um dos scripts, carregue primeiro a função desejada no seu ambiente Python. Em seguida, chame a função passando uma sequência de DNA como argumento para obter seu complemento reverso.