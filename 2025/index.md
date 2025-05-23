# HWMCC'25

This is the 13th competitive event for hardware model checkers.

## Affiliated to [FMCAD'25](https://fmcad.forsyte.at/FMCAD25/)
### October 6 - 10, 2025, Menlo Park, California, USA

## Format

This year we will have the following **four tracks**:

1. Word-level safety without arrays
2. Word-level safety with arrays
3. Bit-level safety
4. Bit-level liveness **(new)**

Note that for track 3 we translate the word-level benchmarks from word-level
track 1 to [AIGER](https://github.com/arminbiere/aiger) bit-level benchmarks.
Note that bit-level tracks will be in **AIGER 1.9** (including [reset functions](#reset-functions)).

### Certificates

In the word-level tracks (1 and 2) producing **BTOR2 counterexamples
will be mandatory**.
The BTOR2 counterexamples will be checked with [BtorSim](https://github.com/Boolector/btor2tools/tree/master/src/btorsim).
As in HWMCC'24, for the **bit-level track, both counterexamples and safety certificates are mandatory**.
The certificates will be checked with [Certifaiger](https://github.com/Froleyks/certifaiger)
and counterexamples with [aigsim](https://github.com/arminbiere/aiger).

As in previous years, the word-level track uses the BTOR2 format described in
[BTOR2 CAV'18 paper](https://link.springer.com/content/pdf/10.1007%2F978-3-319-96145-3_32.pdf).
The [Btor2Tools](https://github.com/hwmcc/btor2tools/)
tool suite provides a generic parser
[Btor2Parser](https://github.com/hwmcc/btor2tools/tree/master/src/btor2parser)
and a simulator
[BtorSim](https://github.com/hwmcc/btor2tools/tree/master/src/btorsim),
which are useful for parsing and random simulation of BTOR2 models, as well as
for witness checking.
There is also a simple bounded model checker
[BtorMC](https://github.com/Boolector/boolector/blob/master/src/btormc.c),
distributed as part of
[Boolector](https://github.com/Boolector/boolector).

### Reset Functions
While the AIGER 1.9 format allows latches to be reset to 0, 1, or remain uninitialized,
reset functions additionally allow latches to be reset to an arbitrary gate.

## Setup

The hardware setup for the competition is as follows: the cluster machines we
use are equipped with
**AMD Ryzen 9 7950X 16-core** processors and **128 GB RAM**,
running **Ubuntu 24.04 LTS**.

Each model checker will have full access to a node, i.e., 16 physical (32
virtual) cores and 128 GB of RAM.
A **memory limit of 120 GB** is enforced with a **time limit of 1 hour**
of wall-clock time.


## Benchmark Submission

Submission deadline for new benchmarks is **August 17, 2025 AoE**.
Please submit safety benchmarks in BTOR2 format and bit-level liveness
benchmarks in AIGER 1.9. Word-level liveness benchmarks are welcome but will not
be used in this year's competition.
If benchmarks have multiple safety/liveness properties, we will split them up
in separate benchmarks with one property each.

Please submit benchmarks to
- [Armin Biere](mailto:biere@cs.uni-freiburg.de)
- [Nils Froleyks](mailto:nils.froleyks@jku.at)
- [Mathias Preiner](mailto:preiner@cs.stanford.edu)

## Model Checker Submission

**Registration and first versions** of model checkers are due on
**September 1, 2025**.

All submission dates are anywhere on earth (AoE). We require the submission to
use **statically compiled binaries** to ensure proper execution in the provided
cluster environment. Make sure that the tool can be **called from any
directory**. Only **one version per model checker** allowed.


Submission process: TBA

### Mandatory Command Line Interface

The **mandatory interface** for each submission is as follows.

**Bit-level track**
```
<tool> <benchmark> <certificate.sat> <certificate.unsat>
```
where
- `<benchmark>` is the AIGER 1.9 benchmark
- `<certificate.sat>` the path of the AIGER counterexample
- `<certificate.unsat>` the path of the safety certificate

The format (binary / ascii) of the certificate.unsat should depend on the file extension of the argument (.aig for binary, .aag for ascii). During the competition we will always expect binary certificates.

**Word-level track**
```
<tool> <benchmark> <certificate.sat>
```

where
- `<benchmark>` is the BTOR2 benchmark
- `<certificate.sat>` the path of the BTOR2 counterexample


**Temporary files** must be written to `/tmp` and should be cleaned up by the model checker before exiting.


## Organization

HWMCC'25 is organized by

- [Armin Biere](https://cca.informatik.uni-freiburg.de/biere),
  [University of Freiburg](https://uni-freiburg.de), Germany
- [Nils Froleyks](http://fmv.jku.at/froleyks), 
  [Johannes Kepler University Linz](http://www.jku.at), Austria
- [Mathias Preiner](https://cs.stanford.edu/~preiner),
  [Stanford University](https://www.stanford.edu), USA
