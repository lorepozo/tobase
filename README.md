# tobase

Base conversion made simple.

__`tobase`__ is a command-line utility to covert to a given base.

## Usage

__`tobase`__ encodes raw data from standard input to standard output.
Out-of-the-box, it can output to any base <= 16, or bases 58 (bitcoin-style)
and 64. For other bases, an alphabet must be provided.

```
Usage: tobase BASE [ALPHABET]

Encodes raw data from stdin.
Set BASE to '-' to use alphabet length
```

### Examples

```sh
$ echo -n 'A' | tobase 10
65

$ echo -n 'tobase' | tobase 58
K9BjCrdnstu

$ echo -n 'A' | tobase '-' '0123456789ABCDEFGHIJ' # base 20
35

$ SECRET='foo'
$ ALPHABET='mycoolALPHAbet~!@#$%^&*()_+'
$ echo -n $SECRET | openssl dgst -sha256 -binary | tobase '-' $ALPHABET
c^ycy@(m!lyP!&o*(t!L&#Hy!tAt_%L#!t~lA+^#!_L$Pe@AH(*A@b
```

## Installation

```sh
git clone https://github.com/lukedmor/tobase
cp tobase/tobase /usr/local/bin/tobase
```
