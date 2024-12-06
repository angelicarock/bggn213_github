# lab6
Angelica Rock (PID 15781397)

# My first function :)

``` r
add <- function(x,y=1){
  x+y
}
```

# Can I just use it?

``` r
add(1,1)
```

    [1] 2

``` r
add(1,100)
```

    [1] 101

``` r
add(c(100,1,100), 1)
```

    [1] 101   2 101

``` r
add(10, 10)
```

    [1] 20

``` r
add(10)
```

    [1] 11

# Q: Make a function “Generate_DNA()” that makes a random nucleotide sequence of any length (user specifies the length)

``` r
  bases <- c("A", "C", "G", "T")
  sequence <- sample(bases, size=100, replace = TRUE)
```

Above is my working snippet, now I can make it into a function

``` r
Generate_DNA <- function(length) {
  bases <- c("A", "C", "G", "T")
  sequence <- sample(bases, size=length, replace = TRUE)
  return(sequence)
}
```

Now I can run this function to get output

``` r
Generate_DNA(10)
```

     [1] "T" "T" "C" "C" "G" "G" "A" "C" "A" "A"

# the paste function is included here because collapse = “” changes the output from “A” “B” “C” etc. to ABC to put the output together so you can copy and paste it into BLAST to get the identities

``` r
Generate_protein <- function(length) {
  amino_acids <- unique(bio3d::aa.table$aa1)[1:20]
  sequence <- sample(amino_acids, size=length, replace = TRUE)
  sequence <- paste(sequence, collapse ="")
  return(sequence)
}
```

Run function

``` r
Generate_protein(10)
```

    [1] "HYLKRKDWFG"

I want to generate sequences of length 6 to 12

``` r
answer <- sapply(6:12, Generate_protein)
```

``` r
cat(paste(">id.", 6:12, "\n", sep = "", answer), sep="\n")
```

    >id.6
    ELFTWV
    >id.7
    GRNRSQY
    >id.8
    SSMQQCDL
    >id.9
    PMYDTSNIL
    >id.10
    LFMCHVFPRL
    >id.11
    ADWEPDRGRDC
    >id.12
    NWEWYWDIFEVA
