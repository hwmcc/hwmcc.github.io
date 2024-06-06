# HWMCC'24

This will be the 12th competitive event for hardware model checkers.

## Affiliated to [FMCAD'24](https://fmcad.forsyte.at/FMCAD24/)
### October 14 - 18, 2024, Prague, Czech Republic

## Format

This year we will have **three tracks** with **single safety** properties:

1. Word-level without arrays
2. Word-level with arrays
3. Bit-level with mandatory safety certificates

Note that for 3) we will translate the word-level benchmarks from 1) to
AIGER bit-level benchmarks.
The certificate will be checked with [Certifaiger](https://github.com/Froleyks/certifaiger).

As in previous years, the word-level track is based on the BTOR2 format, which
is described in
[BTOR2 CAV'18 paper](https://link.springer.com/content/pdf/10.1007%2F978-3-319-96145-3_32.pdf).
The [Btor2Tools](https://github.com/Boolector/btor2tools/)
tool suite provides a generic parser
[Btor2Parser](https://github.com/Boolector/btor2tools/tree/master/src/btor2parser)
and a simulator
[BtorSim](https://github.com/Boolector/btor2tools/tree/master/src/btorsim),
which are useful for parsing and random simulation of BTOR2 models, as well as
for witness checking.
There is also a simple bounded model checker
[BtorMC](https://github.com/Boolector/boolector/blob/master/src/btormc.c),
distributed as part of
[Boolector](https://github.com/Boolector/boolector).


## Setup

TBD

## Benchmarks

Submission deadline for new benchmarks is **August 18, 2024**. Please submit
your benchmarks in BTOR2 format. If benchmarks have multiple safety properties,
we'll split them up in separate benchmarks with one safety property each.

## Submission

Please send model checker and benchmarks submissions to  
- [Armin Biere](mailto:biere@cs.uni-freiburg.de)
- [Nils Froleyks](mailto:nils.froleyks@jku.at)
- [Mathias Preiner](mailto:preiner@cs.stanford.edu)

**Registration and first versions** of model checkers are due on
**September 1, 2024**.

All submission dates are anywhere on earth (AoE).

## Organization

HWMCC'24 is organized by

- [Armin Biere](http://fmv.jku.at/biere),
  [Johannes Keplers University Linz](http://www.jku.at), Austria
- [Nils Froleyks](http://fmv.jku.at/froleyks), 
  [Johannes Keplers University Linz](http://www.jku.at), Austria
- [Mathias Preiner](https://cs.stanford.edu/~preiner),
  [Stanford University](https://www.stanford.edu)
