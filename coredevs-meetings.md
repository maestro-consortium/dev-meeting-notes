# MAESTRO COREDEVS MEETING - Notes


## 2025-03-24

### News

 - [name=Guilhem] crocoddyl v3
     - breaking change (remove dependency to boost shared pointers, now using stl ones)
 - [name=Guilhem] PyPI: coal-library -> coal

### Technical discussions

 - [name=Joris] Branches workflow: How to apply it to pinocchio
     - daily build only run only on default branch (master). Another argument to use devel as the default branch
     - cache is taken from default branch. Again another argument!
     - switch from master(default)/devel to master(stable)/devel(default)
         - no renaming of master to main 
     - announcement to do on all channels, do right away
- [name=Joris] [With pixi, tests link to pinocchio in .pixi/envs folder #2615](https://github.com/stack-of-tasks/pinocchio/issues/2615)
    - tests shoud remain linked to built libraries and not install (use CMake build rpath)


### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 413 days ago, updated 14 days ago, **pr status wip**
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 39 days ago, updated 17 days ago, **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 35 days ago, updated 14 days ago, **pr status wip**
   - choose how to generate bindings (boostpython vs nanobind)
   - difficulty to generate documentation too
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 33 days ago, updated 3 days ago, **pr status wip**
   - remaining issue related to some cache variables in jrl_cmakemodules that do not prefix with project name
   - issue with generation of documentation

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 676 days ago, updated 17 days ago, **pr status wip**
- [#537 Update ROS CI](https://github.com/stack-of-tasks/eigenpy/pull/537)
   - created 7 days ago, updated 7 days ago
   - done and ready for review and merge

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 196 days ago, updated 7 days ago, **pr status wip**
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 188 days ago, updated 17 days ago, **pr status to review**
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 74 days ago, updated 17 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 41 days ago, updated 17 days ago, **pr status wip**
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 40 days ago, updated 17 days ago, **pr status wip**
- [#2590 CI: update ROS](https://github.com/stack-of-tasks/pinocchio/pull/2590)
   - created 32 days ago, updated 17 days ago, **pr status wip**
   - CI is failing
- [#2617 Fix hpp-fcl dependency](https://github.com/stack-of-tasks/pinocchio/pull/2617)
   - created 10 days ago, updated 6 days ago, **pr status wip**
   - target pinocchio-default (interface library), which can or no link on a shared library (generated or not with the template instantiation)
- [#2624 Fix ModelTpl::check() link](https://github.com/stack-of-tasks/pinocchio/pull/2624)
   - created 4 days ago, updated 4 days ago
   - CI fails due to pch, can be merged anyway
- [#2627 Fix ccache cache key](https://github.com/stack-of-tasks/pinocchio/pull/2627)
   - created 3 days ago, updated 3 days ago
   - more to be fixed : cache GitHub Actions wrongly named, issue with pch

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 143 days ago, updated 5 days ago, **pr status wip**
- [#278 croco v3: boost -> std pointers](https://github.com/Simple-Robotics/aligator/pull/278)
   - created 3 days ago, updated 3 days ago
   - see technical discussions
   - upgrade of dependencies + release v0.12


#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 5 days ago, updated 3 days ago, **pr status wip**

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#674 Use double precision for GJK/EPA when coal is compiled in float](https://github.com/coal-library/coal/pull/674)
   - created 6 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2623 Update ROS CI](https://github.com/stack-of-tasks/pinocchio/pull/2623)
   - created 7 days ago
- [#2476 Try to use pre compiled header to accelerate the build](https://github.com/stack-of-tasks/pinocchio/pull/2476)
   - created 132 days ago
- [#2607 Use google benchmark instead of our legacy benchmark system](https://github.com/stack-of-tasks/pinocchio/pull/2607)
   - created 19 days ago
- [#2626 Set back PINOCCHIO_DEFAULT_QUATERNION_NORM_TOLERANCE_VALUE definition](https://github.com/stack-of-tasks/pinocchio/pull/2626)
   - created 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#277 Fix `HistoryCallback` initialization in examples](https://github.com/Simple-Robotics/aligator/pull/277)
   - created 7 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#386 [do not merge] Sync devel and master](https://github.com/Simple-Robotics/proxsuite/pull/386)
   - created 12 days ago
- [#388 Fix pip wheels for windows](https://github.com/Simple-Robotics/proxsuite/pull/388)
   - created 4 days ago




## 2025-03-17

### News
 - [name=Joris] [Proxsuite v0.7.2 released](https://github.com/Simple-Robotics/proxsuite/releases/tag/v0.7.2)

### Technical discussions

- [name=Joris] [Generating pip INSTALLER and METADADA file when installing a Python bindings with CMake](https://github.com/conda-forge/pinocchio-feedstock/issues/139)
    - check with ongoing PR that allows to rely on system dependencies and not pip dependencies
    - Guilhem will get in touch with Silvio
- [name=Guilhem] Branches workflow
    - Past issue with default clone policy (devel branch, often broken) - old way
    - Currently better dev practices.
    - Tools often use main/master by default, need additional config to change
    - Current way, master/main for development, then people use eithers tags or package manager if they want stable version.
    - Ease all our scripts (referring to master)
    - Proposal
        - go for a workflow main ? (instead of master/devel)
        - using a staging branch to perform CI/build all, then automate merging in main ? (GitHub tools or Mergify)
        - prepare a common announcement for all repos ?
            - integrate in the RELEASE thru an issue
            - setup channels for dev announcement?
        - finalize discussions this week

### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 406 days ago, updated 7 days ago, **pr status wip**
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 32 days ago, updated 10 days ago, **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 28 days ago, updated 7 days ago, **pr status wip**
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 26 days ago, updated 10 days ago, **pr status wip**

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 669 days ago, updated 10 days ago, **pr status wip**

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 189 days ago, updated 10 days ago, **pr status to review**
   - await for Pinocchio-4 : back to wip, need to notify them about this
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 181 days ago, updated 10 days ago, **pr status wip**
- [#2476 Try to use pre compiled header to accelerate the build](https://github.com/stack-of-tasks/pinocchio/pull/2476)
   - created 125 days ago, updated 10 days ago, **pr status wip**
   - close PR, negligible gains while increased complexity, no merge
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 67 days ago, updated 10 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 34 days ago, updated 10 days ago, **pr status wip**
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 33 days ago, updated 10 days ago, **pr status wip**
- [#2590 CI: update ROS](https://github.com/stack-of-tasks/pinocchio/pull/2590)
   - created 25 days ago, updated 10 days ago, **pr status wip**
- [#2607 Use google benchmark instead of our legacy benchmark system](https://github.com/stack-of-tasks/pinocchio/pull/2607)
   - created 12 days ago, updated 3 days ago, **pr status wip**
- [#2617 Fix hpp-fcl dependency](https://github.com/stack-of-tasks/pinocchio/pull/2617)
   - created 3 days ago, updated 3 days ago
- [#2620 build(deps): bump ros-industrial/industrial_ci from 8d0620b3c43fc3bb2599b6ede6e0a261a2eced02 to 3e67ec54d63496e076267392148a26229740befc](https://github.com/stack-of-tasks/pinocchio/pull/2620)
   - created 0 days ago, updated 0 days ago
   - await for Guilhem's work (back to wip)
- [#2621 build(deps): bump cachix/install-nix-action from 30 to 31](https://github.com/stack-of-tasks/pinocchio/pull/2621)
   - created 0 days ago, updated 0 days ago
   - merged
- [#2622 build(deps): bump cachix/cachix-action from 15 to 16](https://github.com/stack-of-tasks/pinocchio/pull/2622)
   - created 0 days ago, updated 0 days ago
   - merged

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 136 days ago, updated 3 days ago, **pr status wip**

#### SIMPLE-ROBOTICS/PROXSUITE

- [#386 [do not merge] Sync devel and master](https://github.com/Simple-Robotics/proxsuite/pull/386)
   - created 5 days ago, updated 3 days ago, **pr status wip**


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#665 Float precision](https://github.com/coal-library/coal/pull/665)
   - created 5 days ago
   - Memory gain and possibly performance gain using float precision, while using some algorithms in double to preserve precision where needed
- [#666 flake.lock: Update](https://github.com/coal-library/coal/pull/666)
   - created 5 days ago
- [#668 Add tracy profiling](https://github.com/coal-library/coal/pull/668)
   - created 5 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2528 Add missing Python example for testing](https://github.com/stack-of-tasks/pinocchio/pull/2528)
   - created 84 days ago
- [#2608 Enhacing casting support for multiple floating-point scalars and Casadi and CppAD types](https://github.com/stack-of-tasks/pinocchio/pull/2608)
   - created 10 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#272 Add MPC test/example.](https://github.com/Simple-Robotics/aligator/pull/272)
   - created 20 days ago
- [#274 Allow customization of the initial solution.](https://github.com/Simple-Robotics/aligator/pull/274)
   - created 12 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#384 Fix Visual Studio 17.13 build](https://github.com/Simple-Robotics/proxsuite/pull/384)
   - created 6 days ago
- [#376 black -> ruff](https://github.com/Simple-Robotics/proxsuite/pull/376)
   - created 34 days ago

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#125 Remove absolute path for boost library](https://github.com/Simple-Robotics/proxsuite-nlp/pull/125)
   - created 7 days ago

## 2025-03-10

### News

- [name=Pierre-Guillaume] Maestro to be presented at Agimus exploitation plan workshop (internal EU project presentation)
- [name=Joris] Expected release for eigenpy, pinocchio

### Technical discussions

- [name=Etienne] While TSID not in the scope of Maestro but is used, should we handle release ? No pending changes currently (devel/master) but need to check conda packaging (synchronization with pinocchio) - redo for 3.13 (Joris)
- [name=Wilson] What to do with the 2 Python bindings (boost and nanobind). What if both are loaded? Having both is not good practice. Split pyton bindings. Distribute separately. Legacy is Boost. Boost/nano 2 namespace differents. v2 -> coal-nanobind. Continue to distribute both (boost and nano) for some time to help other projects migrate. No new features on boost binding (all new dev on nano binding). Keep both for 1 year. Need to update find_python2/find_python3 (unified [FindPython](https://cmake.org/cmake/help/latest/module/FindPython.html) module in cmake since 3.12). Need to update jrl_cmakemodules. Release 1.0 by may. then 2.0 that does not supports ubuntu 20.04 (end-of-life)
- [name=Wilson] dicsuss next week about eigen release

### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 399 days ago, updated 3 days ago - **pr status to review**
   - wait for end of life ubuntu 20.04 in may, then PR can be updated -> change to wip
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 25 days ago, updated 3 days ago - **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 21 days ago, updated 3 days ago - **pr status wip**
   - identify binding upstream (eigen), integration with automatic documentation, issue with some versions of doxygen that fail when parsing functions
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 19 days ago, updated 3 days ago - **pr status wip**

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 662 days ago, updated 3 days ago - **pr status wip**

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 182 days ago, updated 3 days ago - **pr status to review**
   - wait for topic_simulation
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 174 days ago, updated 3 days ago - **pr status to review**
   - wait for topic_simulation
- [#2476 Try to use pre compiled header to accelerate the build](https://github.com/stack-of-tasks/pinocchio/pull/2476)
   - created 118 days ago, updated 3 days ago - **pr status wip**
   - work on pause
- [#2528 Add missing Python example for testing](https://github.com/stack-of-tasks/pinocchio/pull/2528)
   - created 77 days ago, updated 3 days ago - **pr status to review**
   - Justin to rebase, process
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 60 days ago, updated 3 days ago - **pr status wip**
   - wait for topic_simulation
- [#2555 build(deps): bump ros-industrial/industrial_ci from 8d0620b3c43fc3bb2599b6ede6e0a261a2eced02 to 8c9b2a6657124a2abf96ef0137f354b0b02d1330](https://github.com/stack-of-tasks/pinocchio/pull/2555)
   - created 49 days ago, updated 3 days ago - **pr status to review**
   - to close, other PR include sha1
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 27 days ago, updated 3 days ago - **pr status wip**
   - wait for topic_simulation
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 26 days ago, updated 3 days ago - **pr status wip**
   - wait for topic_simulation
- [#2590 CI: update ROS](https://github.com/stack-of-tasks/pinocchio/pull/2590)
   - created 18 days ago, updated 3 days ago - **pr status wip**
   - wait for buildfarm ROS (crash due to RAM limit) - splitting the bindings will help
- [#2607 Use google benchmark instead of our legacy benchmark system](https://github.com/stack-of-tasks/pinocchio/pull/2607)
   - created 5 days ago, updated 3 days ago - **pr status wip**
- [#2608 Enhacing casting support for multiple floating-point scalars and Casadi and CppAD types](https://github.com/stack-of-tasks/pinocchio/pull/2608)
   - created 3 days ago, updated 3 days ago - **pr status to review**
   - Issue with cast double to float (pinocchio prevents loss of precision) - need to update PR

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 129 days ago, updated 3 days ago - **pr status to review**
   - need to rebase, work on internal memory alloc, parallelisation, change to wip
- [#272 Add MPC test/example.](https://github.com/Simple-Robotics/aligator/pull/272)
   - created 13 days ago, updated 3 days ago - **pr status to review**
   - ongoing review by Wilson
- [#274 Allow customization of the initial solution.](https://github.com/Simple-Robotics/aligator/pull/274)
   - created 5 days ago, updated 3 days ago - **pr status to review**
   - ongoing review by Wilson

#### SIMPLE-ROBOTICS/PROXSUITE

- [#376 black -> ruff](https://github.com/Simple-Robotics/proxsuite/pull/376)
   - created 27 days ago, updated 3 days ago - **pr status to review**
   - Joris to check CI issues - can be merged


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#662 CI: update ros distros](https://github.com/coal-library/coal/pull/662)
   - created 18 days ago - **no pr tag**
- [#664 Fix typo in Readme section title](https://github.com/coal-library/coal/pull/664)
   - created 6 days ago - **no pr tag**

#### STACK-OF-TASKS/EIGENPY

- [#536 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/536)
   - created 7 days ago - **no pr tag**

#### STACK-OF-TASKS/PINOCCHIO

- [#2606 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2606)
   - created 5 days ago - **no pr tag**
- [#2591 CMake: fix for hpp-fcl/coal v3](https://github.com/stack-of-tasks/pinocchio/pull/2591)
   - created 16 days ago - **no pr tag**

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#124 Update pixi lockfile](https://github.com/Simple-Robotics/proxsuite-nlp/pull/124)
   - created 9 days ago - **no pr tag**
    
## 2025-03-03

### News

 - [name=Pierre-Guillaume] Maestro will attend [Automatica](https://automatica-munich.com/en/trade-fair/) (Munich, 24-27 June) along Inria teams with a dedicated booth
 - [name=Joris] Mimic joint support Release: articulation following the motion of another one with an affine transformation

### Technical discussions

- [name=Pierre-Guillaume] Comments on PR labels and CONTRIBUTING.md file, schedule deployement with the coming days
     - see the [associated note](https://notes.inria.fr/PXecdWGFRG2Y7oMIarZICQ#)
     - "draft" vs "pr wip". What's the difference ?
     - human-supervision vs automatization (up to 30 PR a week ok?)
     - labels only managed by maintainers, mergify (external service)
- [name=Joris] Re: How to split main library/bindings build (coal [PR #658](https://github.com/coal-library/coal/pull/658)) 


### PR to review

#### COAL-LIBRARY/COAL

- [#320 Benchmark for Nesterov-accelerated GJK vs. GJK timings [WIP]](https://github.com/coal-library/coal/pull/320)
   - created 962 days ago, updated 743 days 
   - old PR to close (no more work - Louis)
- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 392 days ago, updated 392 days ago
   - lib expose static and shared - currently link to static, link to shared instead ?
   - reentrant on static only ? linked to old ubuntu ? check with JosephM 
   - still need to hide symbols on Mac (gcc flag)
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 18 days ago, updated 10 days ago
   - see technical discussion
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 14 days ago, updated 13 days ago
   - nanobind allows to benefit from the cross-versioning on Python 3.8-3.13
   - maintenance cost of eigenpy long-term
   - possible issues with users using it through pinocchio: need of a double support on both eigenpy and nanobind
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 12 days ago, updated 12 days ago
   - see technical discussion
- [#662 CI: update ros distros](https://github.com/coal-library/coal/pull/662)
   - created 11 days ago, updated 7 days ago
   - PR ready for merge
   - ref https://github.com/jrl-umi3218/jrl-cmakemodules/pull/735

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 655 days ago, updated 75 days ago
   - As discussed last week, low priority: Justin will work on it when available

#### STACK-OF-TASKS/PINOCCHIO

- [#2204 Introduced inertia/symmetric3 minus operators](https://github.com/stack-of-tasks/pinocchio/pull/2204)
   - created 333 days ago, updated 258 days ago
   - Joris to send: inquire about the log cholesky
- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 175 days ago, updated 98 days ago
   - wait for pinocchio 4
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 167 days ago, updated 13 days ago
   - wait for pinocchio 4
- [#2476 Try to use pre compiled header to accelerate the build](https://github.com/stack-of-tasks/pinocchio/pull/2476)
   - created 111 days ago, updated 110 days ago
   - back to wip/draft, wait for contributor
- [#2528 Add missing Python example for testing](https://github.com/stack-of-tasks/pinocchio/pull/2528)
   - created 70 days ago, updated 14 days ago
   - rebase and merge (mergify can add rebase button - different fron github one which is merge in fact)
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 53 days ago, updated 47 days ago
   - wait for pinocchio 4
- [#2555 build(deps): bump ros-industrial/industrial_ci from 8d0620b3c43fc3bb2599b6ede6e0a261a2eced02 to 8c9b2a6657124a2abf96ef0137f354b0b02d1330](https://github.com/stack-of-tasks/pinocchio/pull/2555)
   - created 42 days ago, updated 7 days ago
- [#2557 Add <include\> tag support in MJCF parser](https://github.com/stack-of-tasks/pinocchio/pull/2557)
   - created 38 days ago, updated 16 days ago
   - send email (Megane) - use git coauthor?
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 20 days ago, updated 3 days ago
   - wait for pinocchio 4
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 19 days ago, updated 17 days ago
   - wait for pinocchio 4
- [#2590 CI: update ROS](https://github.com/stack-of-tasks/pinocchio/pull/2590)
   - created 11 days ago, updated 11 days ago
   - not yet ready: build-farm ros suffers from lack of RAM
   - ongoing work by Guilhem
- [#2591 CMake: fix for hpp-fcl/coal v3](https://github.com/stack-of-tasks/pinocchio/pull/2591)
   - created 9 days ago, updated 9 days ago
   - condition was breaking
   - ready: already active on the ros farm

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 122 days ago, updated 3 days ago
- [#272 Add MPC test/example.](https://github.com/Simple-Robotics/aligator/pull/272)
   - created 6 days ago, updated 6 days ago
- [#273 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/273)
   - created 2 days ago, updated 2 days ago
   - ready to be merged

#### SIMPLE-ROBOTICS/PROXSUITE

- [#376 black -> ruff](https://github.com/Simple-Robotics/proxsuite/pull/376)
   - created 20 days ago, updated 20 days ago
   - following Stéphane's work, Guilhem is working on it

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#124 Update pixi lockfile](https://github.com/Simple-Robotics/proxsuite-nlp/pull/124)
   - created 2 days ago, updated 2 days ago
   - merged

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#663 Update pixi lockfile](https://github.com/coal-library/coal/pull/663)
   - created 2 days ago

#### STACK-OF-TASKS/EIGENPY

- [#535 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/535)
   - created 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2593 build(deps): bump prefix-dev/setup-pixi from 0.8.2 to 0.8.3](https://github.com/stack-of-tasks/pinocchio/pull/2593)
   - created 7 days ago
- [#2441 Extend Support for Mimic Joint](https://github.com/stack-of-tasks/pinocchio/pull/2441)
   - created 154 days ago
- [#2599 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2599)
   - created 2 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#375 Replace `!= None` with `is not None` in Python bindings](https://github.com/Simple-Robotics/proxsuite/pull/375)
   - created 20 days ago

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#92 Add BFGS ](https://github.com/Simple-Robotics/proxsuite-nlp/pull/92)
   - created 276 days ago
    
## 2025-02-24

### News

- First CoreDevs meeting

### Technical discussions

- [name=Joris] How to split main library/bindings build (coal PR #658)
    - how to ease the build of projects and Python bindings
    - 3 approaches
        - "if" in cmakefiles
        - in the same repo, split cmakelist with with project/sub-project which can be activated or compiled separately (slight more complex). Issue with jrl-cmakemodules.
        - have 2 repositories (involves a lot of work)
    - 2 POCs currently (approaches 1 & 2), ongoing
    - example SOFA: https://sofa-framework.github.io/doc/programming-with-sofa/create-your-plugin/#plugin-architecture

### PR to review

#### COAL-LIBRARY/COAL

- [#320 Benchmark for Nesterov-accelerated GJK vs. GJK timings [WIP]](https://github.com/coal-library/coal/pull/320)
   - created 952 days ago, updated 733 days ago
   - Louis assigned on it (not a priority so far) - standby
- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 382 days ago, updated 382 days ago
   - still meaningful
   - define private linking (hiding all qhullsymbols) - check mac vs linux
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 8 days ago, updated 2 days ago
   - see technical discussion (1st POC)
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 4 days ago, updated 3 days ago
   - main effort eigenpy move to nano (Lucas and Wilson assigned)
   - change to label WIP
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 2 days ago, updated 2 days ago
   - see technical discussion (2nd POC)
- [#661 subscribe to ROS buildfarm mails](https://github.com/coal-library/coal/pull/661)
   - created 1 days ago, updated 1 days ago
   - merged
- [#662 CI: update ros distros](https://github.com/coal-library/coal/pull/662)
   - created 1 days ago, updated 1 days ago
   - Guilhem assigned. Need to filter old ros distros

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 645 days ago, updated 65 days ago
   - PR needs to be cleaned (packaging) - Justin assigned, low priority
- [#534 subscribe to ROS buildfarm mails](https://github.com/stack-of-tasks/eigenpy/pull/534)
   - created 1 days ago, updated 1 days ago
   - merged


#### STACK-OF-TASKS/PINOCCHIO

- [#2591 CMake: fix for hpp-fcl/coal v3](https://github.com/stack-of-tasks/pinocchio/pull/2591)
    - Prefer to wait for topic-simulation to be merged (Pinocchio v4)
- [#2590 CI: update ROS](https://github.com/stack-of-tasks/pinocchio/pull/2590)
    - Reformatting CMake
    - Prefer to wait for topic-simulation to be merged (Pinocchio v4)
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
    - Just a PoC 
    - Manage header includes in Pinocchio. Applied to all codebase when approved
- [#2557 Add \<include\> tag support in MJCF parser](https://github.com/stack-of-tasks/pinocchio/pull/2557)
    - Going to be included in Pinocchio v4, minor PR
    - Need to contact the contributor
- [#2555 build(deps): bump ros-industrial/industrial_ci](https://github.com/stack-of-tasks/pinocchio/pull/2555)
    - PR dependabot
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
    - PR attempting to improve performances on Eigen expression
    - Waiting for topic-simulation (Pinocchio v4)
- [#2528 Add missing Python example for testing](https://github.com/stack-of-tasks/pinocchio/pull/2528)
    - Rebase and merge to improve test coverage
- [#2476 Try to use pre compiled header to accelerate the build](https://github.com/stack-of-tasks/pinocchio/pull/2476)
    - Wilson conducted additional experiments in Aligator. To be rediscussed with him
- [#2441 Extend Support for Mimic Joint](https://github.com/stack-of-tasks/pinocchio/pull/2441)
    - Almost ready. Small discussion wrt integrate
    - Python binding issue (warning to deal with models with mimic joints and algos that do not support mimics).
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
    - Need to check in details
- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
    - Need to check in details
- [#2204 Introduced inertia/symmetric3 minus operators](https://github.com/stack-of-tasks/pinocchio/pull/2204)
    - Need check on matrices

    
#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 112 days ago, updated 11 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#376  black -> ruff](https://github.com/Simple-Robotics/proxsuite/pull/376)
   - created 15 days agom, updated 14 days ago
   - conflicts to be solved

### PR merged within the week
