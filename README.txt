This repository contains the case studies for the TACAS 2017 submission
"Interpolation-Based GR(1) Assumptions Refinement"

Each folder contains:
- A .rat file
- A subdirectory named counterstrategy0

The .rat file contains the specification of assumption and guarantees, along with
all the refinements returned by the approach.
It can be loaded in the RATSY tool:
http://rat.fbk.eu/ratsy/

The subdirectory is the root of a directory structure with all the counterstrategies, counterplays,
translations and interpolants computed throughout the execution.

Counterstrategies and refinements are numbered according to their position in the recursion
tree. 'counterstrategy0' is the counterstrategy computed from the initial, unrealizable specification.
The alternative refinements computed to rule out 'counterstrategy0' are named 'ref1',
'ref2'.... They are included in the .rat files.
If 'ref<x>' is insufficient to reach realizability, the counterstrategy named 'counterstrategy<x>' is computed
by RATSY. In order to rule out 'counterstrategyx', our approach generates the alternative refinements
indexed as 'ref<x>_1', 'ref<x>_2'..., included in the .rat file.

Given this indexing criterion, the subfolder named 'counterstrategy<x>' contains:
- the files 'graph_with_signals.dot' and 'graph.info' containing the counterstrategy and
its state valuations
- a sequence of directories 'unrolling0','unrolling1'..., each for an unrolling step executed
for the current refinement step
- a file <name_case_study>_Assumptions containing the assumptions in the unrealizable core
- a file <name_case_study>_Guarantees containing the assumptions in the unrealizable core

In each 'unrolling<y>' directory there are four files:
- a 'path' file containing the extracted unrolled counterplay
- the translated counterplay
- the translated guarantees
- the interpolant computed by MathSAT

ADDITIONAL FILES IN AMBA02Example
The files of the additional test executed on AMBA02 are in AMBA02Example/counterstrategy0/counterstrategy5/alternativepath<z>.
It contains the translations and interpolants computed on three different paths of counterstrategy5.
