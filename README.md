# Cryptanalysis of RSA Variants with Modified Euler Quotient

## Introduction

This is a Python implementation of lattice-based small private key attack proposed in **Cryptanalysis of RSA Variants with Modified Euler Quotient**[^MEQRSA].

## Requirements

- [**SageMath**](https://www.sagemath.org/) 9.5 with Python 3.10

You can check your SageMath Python version using the following command:

```commandline
$ sage -python --version
Python 3.10.12
```

Note: If your SageMath Python version is older than 3.9.0, some features in given scripts might not work.

## Usage

The standard way to run the attack with the specific parameters requires passing them as command line arguments `sage -python attack.py <modulus_bit_length> <delta> <s>`. For instance, to run the attack with $\ell=512$, $\delta=0.53$, and $s=5$, please run `sage -python attack.py 512 0.53 5`:

```commandline
MEQRSA$ sage -python attack.py 512 0.53 5
The parameters:
N = 5302370728151146643573602277543959859167110186088694779545236841733740983055014063430848984694116359839582474549196804700275148680808708489269724971662181
e = 22090019937033368929183773318304980662691702815227576837695875299934663526387494644824335476058089001179041318851084126714255456432467553819156983311948126720480646840280428225211703421259865205740611957298689020650368826127701944575084934822608986087511978495725566422154942857890033755486583899463190242643
Found primes:
p = 74390114322681263284537027195008925538547288620398704370486626537893930613959
q = 71277894602380977249412811716466945287295375713199970878412740868044756345459
The attack costs 1.523 seconds...
```

For instance, to run the attack with $\ell=256$, $\delta=0.545$, and $s=9$, please run `sage -python attack.py 256 0.545 9`:

```commandline
MEQRSA$ sage -python attack.py 256 0.545 9
The parameters:
N = 43266316408363460228399167041523071888524066986883501250102276591131373293413
e = 918196045073333380570704556308914011469974196897632105366090623657645231475046659462567216139248461111276148598221122899583944636539967401894273463670359
Found primes:
p = 246091228931821363913849266866748853531
q = 175814134441785522227235664416432676223
The attack costs 13.056 seconds...
```

## Notes

All the details of the numerical attack experiments are recorded in the `attack.log` file. A more efficient lattice reduction algorithm [flatter](https://github.com/keeganryan/flatter) is used and `USE_FLATTER = True`.

[^MEQRSA]: Zheng M., Kunihiro N., Hu H., "Cryptanalysis of RSA Variants with Modified Euler Quotient" | [Slides](https://mengcezheng.github.io/docs/AFRICACRYPT18.pdf)
