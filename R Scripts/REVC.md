# Encontrando o Complemento Reverso de uma Sequência de DNA em R

Este documento contém cinco scripts distintos em R para encontrar o complemento reverso de uma sequência de DNA.

## Scripts

### Script 1: Uso de dicionário para mapeamento de complementos e função `rev`
```
reverse_complement_r1 <- function(dna) {
  complement <- setNames(c('T', 'G', 'C', 'A'), c('A', 'C', 'G', 'T'))
  return(paste(rev(complement[unlist(strsplit(dna, ''))]), collapse = ''))
}
```
### Script 2: Uso de dicionário com `sapply` e função `rev`
```
reverse_complement_r2 <- function(dna) {
  complement <- setNames(c('T', 'G', 'C', 'A'), c('A', 'C', 'G', 'T'))
  return(paste(sapply(strsplit(dna, '')[[1]], function(x) complement[x]), collapse = ''))
}
```
### Script 3: Uso de `gsubfn` para substituição e função `rev`
```
library(gsubfn)
reverse_complement_r3 <- function(dna) {
  complement <- list(A = 'T', T = 'A', C = 'G', G = 'C')
  return(paste(rev(gsubfn('.', complement, dna)), collapse = ''))
}
```

### Script 4: Uso de loop `for` com construção de string
```
reverse_complement_r4 <- function(dna) {
  complement <- setNames(c('T', 'G', 'C', 'A'), c('A', 'C', 'G', 'T'))
  dna_array <- unlist(strsplit(dna, ''))
  result <- character(length(dna_array))
  for(i in seq_along(dna_array)) {
    result[i] <- complement[dna_array[i]]
  }
  return(paste(rev(result), collapse = ''))
}
```
## Uso

Para usar qualquer um dos scripts em R, primeiro carregue a função desejada no seu ambiente R. Em seguida, chame a função passando uma sequência de DNA como argumento para obter seu complemento reverso.
"""