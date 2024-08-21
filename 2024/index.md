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
The certificate will be checked with [Certifaiger](https://github.com/Froleyks/certifaiger)
and counter examples with [aigsim](http://fmv.jku.at/aiger).

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

The hardware setup for the competition is as follows: the cluster machines we
use are equipped with
**AMD Ryzen 9 7950X 16-core** processors and **128 GB RAM**,
running **Ubuntu 20.04 LTS**.

Each model checker will have full access to a node, i.e., 16 (physical) cores
and 128 GB of RAM.
A **memory limit of 120 GB**  will be enforced with a **time limit of 1 hour**
of wall-clock time.


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

All submission dates are anywhere on earth (AoE). Make sure that the submission
can be **executed under Ubuntu 20.04 LTS**. The safest bet is to provide
**statically linked binaries**.

### Bit-Level Certificate Output

Certificates should be written to an output file in the **current working
directory**, ideally to a file called `certificate.aig` (for binary AIGER) and
`certificate.aag` (for ASCII AIGER). If the name of the certificate is
different, please mention this in your submission.


## Organization

HWMCC'24 is organized by

- [Armin Biere](https://cca.informatik.uni-freiburg.de/biere),
  [University of Freiburg](https://uni-freiburg.de), Germany
- [Nils Froleyks](http://fmv.jku.at/froleyks), 
  [Johannes Kepler University Linz](http://www.jku.at), Austria
- [Mathias Preiner](https://cs.stanford.edu/~preiner),
  [Stanford University](https://www.stanford.edu), USA
