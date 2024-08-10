
[![Build
Status](https://app.travis-ci.com/thekvs/zstdr.svg?branch=master)](https://app.travis-ci.com/thekvs/zstdr)
[![CRAN
Status](http://www.r-pkg.org/badges/version/zstdr)](https://cran.r-project.org/package=zstdr)

## About

This package provides simple R bindings to the [Zstandard compression
library](http://facebook.github.io/zstd/).

## Benchmarks

See [benchmarks](Benchmarks.md) for comparison with other compression
algorithms.

## Installation

To install from CRAN:

``` r
install.packages('zstdr')
```

To install development version from GitHub:

``` r
devtools::install_github("thekvs/zstdr")
```

## Usage

``` r
library(zstdr)

data_file <- file.path(R.home(), "COPYING")
data <- readBin(data_file, raw(), file.info(data_file)$size)
compressed <- zstdCompress(data)
stopifnot(identical(data, zstdDecompress(compressed)))
```

## Links

-   [zstandard official site](http://facebook.github.io/zstd/)
-   [zstandard C API
    documentation](http://facebook.github.io/zstd/zstd_manual.html)
