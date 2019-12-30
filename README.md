
# graphstreamjars

Java Archive Wrapper Supporting the ‘awsathena’ Package

## Description

Contains all supporting JARs for working with the GraphStream Java APIs.
(<http://graphstream-project.org/>). Version number matches version
number of included ‘graphstreamjars’ libraries.

## Installation

``` r
devtools::install_git("git@git.sr.ht:~hrbrmstr/graphstreamjars")
# OR
devtools::install_gitlab("hrbrmstr/graphstreamjars")
# OR
devtools::install_github("hrbrmstr/graphstreamjars")
```

## Usage

``` r
library(rJava)
```

    ## 
    ## Attaching package: 'rJava'

    ## The following object is masked from 'package:bit':
    ## 
    ##     clone

``` r
library(graphstreamjars)

packageVersion("graphstreamjars")
```

    ## [1] '1.3.0'

``` r
library(graphstreamjars)

SingleGraph <- J("org.graphstream.graph.implementations.SingleGraph")

(graph <- .jnew(SingleGraph, "Tutorial 1"))
```

    ## [1] "Java-Object{Tutorial 1}"

``` r
graph$addNode("A")
```

    ## [1] "Java-Object{A}"

``` r
graph$addNode("B")
```

    ## [1] "Java-Object{B}"

``` r
graph$addNode("C")
```

    ## [1] "Java-Object{C}"

``` r
graph$addEdge("AB", "A", "B")
```

    ## [1] "Java-Object{AB[A--B]}"

``` r
graph$addEdge("BC", "B", "C")
```

    ## [1] "Java-Object{BC[B--C]}"

``` r
graph$addEdge("CA", "C", "A")
```

    ## [1] "Java-Object{CA[C--A]}"

``` r
graph$setStrict(FALSE)
graph$setAutoCreate(TRUE)
graph$addEdge("AB", "A", "B")
```

    ## [1] "Java-Object{AB[A--B]}"

``` r
graph$addEdge("BC", "B", "C")
```

    ## [1] "Java-Object{BC[B--C]}"

``` r
graph$addEdge("CA", "C", "A")
```

    ## [1] "Java-Object{CA[C--A]}"

``` r
(A <- graph$getNode("A"))
```

    ## [1] "Java-Object{A}"

``` r
(AB <- graph$getEdge("AB"))
```

    ## [1] "Java-Object{AB[A--B]}"

``` r
ni <- graph$getNodeIterator()

while(ni$hasNext()) {
  print(.jrcall(ni, "next"))
}
```

    ## [1] "Java-Object{A}"
    ## [1] "Java-Object{B}"
    ## [1] "Java-Object{C}"

## `graphstreamjars` Metrics

| Lang  | \# Files |  (%) | LoC |  (%) | Blank lines |  (%) | \# Lines |  (%) |
| :---- | -------: | ---: | --: | ---: | ----------: | ---: | -------: | ---: |
| XML   |        1 | 0.08 |  66 | 0.32 |           0 | 0.00 |        0 | 0.00 |
| Maven |        2 | 0.17 |  58 | 0.28 |           9 | 0.23 |        6 | 0.08 |
| Java  |        2 | 0.17 |  28 | 0.14 |           5 | 0.13 |       18 | 0.24 |
| Rmd   |        1 | 0.08 |  27 | 0.13 |          20 | 0.51 |       24 | 0.32 |
| R     |        5 | 0.42 |  15 | 0.07 |           1 | 0.03 |       28 | 0.37 |
| make  |        1 | 0.08 |  13 | 0.06 |           4 | 0.10 |        0 | 0.00 |
