
[![Project Status: WIP – Initial development is in progress, but there
has not yet been a stable, usable release suitable for the
public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
[![Signed
by](https://img.shields.io/badge/Keybase-Verified-brightgreen.svg)](https://keybase.io/hrbrmstr)
![Signed commit
%](https://img.shields.io/badge/Signed_Commits-100%25-lightgrey.svg)
[![Linux build
Status](https://travis-ci.org/hrbrmstr/graphstreamjars.svg?branch=master)](https://travis-ci.org/hrbrmstr/graphstreamjars)  
![Minimal R
Version](https://img.shields.io/badge/R%3E%3D-3.2.0-blue.svg)
![License](https://img.shields.io/badge/License-LGPL-blue.svg)

# graphstreamjars

Java Archive Wrapper Supporting the ‘graphstream’ Package

## Description

Contains all supporting JARs for working with the GraphStream Java APIs.
(<http://graphstream-project.org/>) Version number matches version
number of included ‘graphstreamjars’ libraries.

## What’s Inside The Tin

The following functions are implemented:

## Installation

``` r
remotes::install_git("https://git.rud.is/hrbrmstr/graphstreamjars.git")
# or
remotes::install_git("https://git.sr.ht/~hrbrmstr/graphstreamjars")
# or
remotes::install_gitlab("hrbrmstr/graphstreamjars")
# or
remotes::install_bitbucket("hrbrmstr/graphstreamjars")
# or
remotes::install_github("hrbrmstr/graphstreamjars")
```

NOTE: To use the ‘remotes’ install options you will need to have the
[{remotes} package](https://github.com/r-lib/remotes) installed.

## Usage

``` r
library(rJava)
library(graphstreamjars)

packageVersion("graphstreamjars")
## [1] '1.3.0'
```

``` r
library(graphstreamjars)

SingleGraph <- J("org.graphstream.graph.implementations.SingleGraph")

(graph <- .jnew(SingleGraph, "Tutorial 1"))
## [1] "Java-Object{Tutorial 1}"

graph$addNode("A")
## [1] "Java-Object{A}"
graph$addNode("B")
## [1] "Java-Object{B}"
graph$addNode("C")
## [1] "Java-Object{C}"
graph$addEdge("AB", "A", "B")
## [1] "Java-Object{AB[A--B]}"
graph$addEdge("BC", "B", "C")
## [1] "Java-Object{BC[B--C]}"
graph$addEdge("CA", "C", "A")
## [1] "Java-Object{CA[C--A]}"

graph$setStrict(FALSE)
graph$setAutoCreate(TRUE)
graph$addEdge("AB", "A", "B")
## [1] "Java-Object{AB[A--B]}"
graph$addEdge("BC", "B", "C")
## [1] "Java-Object{BC[B--C]}"
graph$addEdge("CA", "C", "A")
## [1] "Java-Object{CA[C--A]}"

(A <- graph$getNode("A"))
## [1] "Java-Object{A}"

(AB <- graph$getEdge("AB"))
## [1] "Java-Object{AB[A--B]}"

ni <- graph$getNodeIterator()

while(ni$hasNext()) {
  print(.jrcall(ni, "next"))
}
## [1] "Java-Object{A}"
## [1] "Java-Object{B}"
## [1] "Java-Object{C}"
```

## `graphstreamjars` Metrics

| Lang  | \# Files |  (%) | LoC |  (%) | Blank lines |  (%) | \# Lines |  (%) |
| :---- | -------: | ---: | --: | ---: | ----------: | ---: | -------: | ---: |
| XML   |        1 | 0.08 |  66 | 0.32 |           0 | 0.00 |        0 | 0.00 |
| Maven |        2 | 0.17 |  58 | 0.28 |           9 | 0.22 |        6 | 0.08 |
| Rmd   |        1 | 0.08 |  29 | 0.14 |          21 | 0.52 |       26 | 0.33 |
| Java  |        2 | 0.17 |  28 | 0.13 |           5 | 0.12 |       18 | 0.23 |
| R     |        5 | 0.42 |  15 | 0.07 |           1 | 0.02 |       28 | 0.36 |
| make  |        1 | 0.08 |  13 | 0.06 |           4 | 0.10 |        0 | 0.00 |
