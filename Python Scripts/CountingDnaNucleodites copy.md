# Contador de Nucleotídeos em R

Este repositório contém cinco scripts distintos em R para contar as ocorrências dos nucleotídeos A, C, G e T em uma sequência de DNA.

## Scripts

Cada script abaixo oferece uma abordagem diferente para resolver o problema de contar nucleotídeos em uma cadeia de DNA.

### Script 1: Usando a biblioteca stringr

```r
library(stringr)

count_nucleotides_1 <- function(dna) {
  a_count <- str_count(dna, "A")
  c_count <- str_count(dna, "C")
  g_count <- str_count(dna, "G")
  t_count <- str_count(dna, "T")
  return(c(A=a_count, C=c_count, G=g_count, T=t_count))
}
```

### Script 2: Usando gregexpr e length

```r
count_nucleotides_2 <- function(dna) {
  a_count <- length(unlist(gregexpr("A", dna))) - 1
  c_count <- length(unlist(gregexpr("C", dna))) - 1
  g_count <- length(unlist(gregexpr("G", dna))) - 1
  t_count <- length(unlist(gregexpr("T", dna))) - 1
  return(c(A=a_count, C=c_count, G=g_count, T=t_count))
}
```

### Script 3: Usando table e strsplit

```r
count_nucleotides_3 <- function(dna) {
  nucleotide_counts <- table(unlist(strsplit(dna, "")))
  return(nucleotide_counts[c("A", "C", "G", "T")])
}
```

### Script 4: Usando um loop for e um vetor de contagem

```r
count_nucleotides_4 <- function(dna) {
  counts <- c(A=0, C=0, G=0, T=0)
  for (i in strsplit(dna, "")[[1]]) {
    counts[i] <- counts[i] + 1
  }
  return(counts)
}
```

### Script 5: Usando sapply para aplicar gregexpr e length

```r
count_nucleotides_5 <- function(dna) {
  nucleotides <- c("A", "C", "G", "T")
  counts <- sapply(nucleotides, function(n) length(unlist(gregexpr(n, dna))) - 1)
  names(counts) <- nucleotides
  return(counts)
}
```

## Uso

Para usar qualquer um dos scripts, primeiro carregue a função correspondente no seu ambiente R. Em seguida, chame a função com uma sequência de DNA como argumento para obter as contagens de cada nucleotídeo.
