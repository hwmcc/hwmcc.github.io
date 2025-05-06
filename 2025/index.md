# HWMCC'25

This was be the 13th competitive event for hardware model checkers.

## Affiliated to [FMCAD'25](https://fmcad.forsyte.at/FMCAD25/)
### October 6 - 10, 2025, Menlo Park, California, USA

## Format

This year we will have the following **five tracks**:

1. Word-level safety without arrays
2. Word-level safety with arrays
3. Word-level liveness (with or without arrays) **(new)**
4. Bit-level safety
5. Bit-level liveness **(new)**

Note that for track 4 we translate the word-level benchmarks from word-level
track 1 to [AIGER](https://github.com/arminbiere/aiger) bit-level benchmarks.
Track 3 will be contingent on benchmark availability.
Note that bit-level tracks will be in AIGER 1.9 (including reset functions).

### Certificates

In the word-level tracks (1 and 2) producing **BTOR2 counterexample 
(sat) will be mandatory**.
The BTOR2 counterexamples will be checked with [BtorSim](https://github.com/Boolector/btor2tools/tree/master/src/btorsim).
As in HWMCC'24, in the **bit-level safety certificates will be mandatory**.
The bit-level certificates will be checked with [Certifaiger](https://github.com/Froleyks/certifaiger)
and counterexamples with [aigsim](https://github.com/arminbiere/aiger).

As in previous years, the word-level track was based on the BTOR2 format, which
is described in
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


## Setup

The hardware setup for the competition is as follows: the cluster machines we
use are equipped with
**AMD Ryzen 9 7950X 16-core** processors and **128 GB RAM**,
running **Ubuntu 24.04 LTS**.

Each model checker will have full access to a node, i.e., 16 (physical) cores
and 128 GB of RAM.
A **memory limit of 120 GB**  is enforced with a **time limit of 1 hour**
of wall-clock time.


## Benchmark Submission

Submission deadline for new benchmarks is **August 17, 2025 AoE**.
Please submit your benchmarks in BTOR2 format.
If benchmarks have multiple safety/liveness properties, we will split them up
in separate benchmarks with one property each.
Bit-level AIGER benchmarks with liveness properties are also welcome.

Please submit benchmarks to
- [Armin Biere](mailto:biere@cs.uni-freiburg.de)
- [Nils Froleyks](mailto:nils.froleyks@jku.at)
- [Mathias Preiner](mailto:preiner@cs.stanford.edu)

## Model Checker Submission

**Registration and first versions** of model checkers are due on
**September 1, 2025**.

All submission dates are anywhere on earth (AoE). We require the submission to
use **statically compiled binaries** to ensure proper execution in the provided
cluster environment. If the submission relies on Python, make sure that the
tool can be **called from any directory**.


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
- `<certificater.unsat>` the path of the safety certificate


**Word-level track**
```
<tool> <benchmark> <certificate.sat>
```

where
- `<benchmark>` is the BTOR2 benchmark
- `<certificate.sat>` the path of the BTOR2 counterexample


**Temporary files** must be written to `/tmp`.


## Organization

HWMCC'25 is organized by

- [Armin Biere](https://cca.informatik.uni-freiburg.de/biere),
  [University of Freiburg](https://uni-freiburg.de), Germany
- [Nils Froleyks](http://fmv.jku.at/froleyks), 
  [Johannes Kepler University Linz](http://www.jku.at), Austria
- [Mathias Preiner](https://cs.stanford.edu/~preiner),
  [Stanford University](https://www.stanford.edu), USA
