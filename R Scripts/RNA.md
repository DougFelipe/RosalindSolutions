# Transcrição de DNA para RNA em R

Este documento contém cinco scripts distintos em R para transcrever uma sequência de DNA em RNA, substituindo todas as ocorrências de 'T' por 'U'.

## Soluções em R

### Solução 1: Substituição direta com `chartr`
``` 
transcribe_dna_to_rna1 <- function(dna) {
  return(chartr("T", "U", dna))
}
``` 
### Solução 2: Uso de `gsub`
``` 
transcribe_dna_to_rna2 <- function(dna) {
  return(gsub("T", "U", dna))
}
``` 
### Solução 3: Uso de `str_replace_all` da biblioteca `stringr`
``` 
library(stringr)
transcribe_dna_to_rna3 <- function(dna) {
  return(str_replace_all(dna, "T", "U"))
}
``` 
### Solução 4: Usando compreensão de lista com `sapply`
``` 
transcribe_dna_to_rna4 <- function(dna) {
  nucleotides <- unlist(strsplit(dna, ""))
  rna <- sapply(nucleotides, function(x) ifelse(x == "T", "U", x))
  return(paste(rna, collapse = ""))
}
``` 
### Solução 5: Usando um loop `for` com construção de string
``` 
transcribe_dna_to_rna5 <- function(dna) {
  rna <- vector("character", nchar(dna))
  for (i in seq_along(rna)) {
    rna[i] <- ifelse(substr(dna, i, i) == "T", "U", substr(dna, i, i))
  }
  return(paste(rna, collapse = ""))
}
``` 
## Uso

Para usar qualquer uma dessas funções em R, primeiro carregue a função desejada no seu ambiente R. Em seguida, chame a função passando uma sequência de DNA como argumento para obter a sequência de RNA transcrita.
