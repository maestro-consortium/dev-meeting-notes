# MAESTRO COREDEVS MEETING - Notes



## 2025-11-03

### News

 - [name=Joris] Départ de Mégane et arrivée de Jeanne

### Technical discussions

 - [name=Joris] Check organisation rules in Github
 - 
#### simple-robotics/proxsuite

 - Items to discuss:
   - [#426 eigen 5 support](https://github.com/Simple-Robotics/proxsuite/issues/426)
       - must activate all dependencies (casadi depends on proxsuite)
       - hard to track, no time yet to investigate
       - ignore these 3 tests temporarily ?

### PR to review

#### COAL-LIBRARY/COAL

- [#774 Update pixi.toml](https://github.com/coal-library/coal/pull/774)
   - Created 10 days ago, updated 3 days ago, no status
       - Issue with install path when using pixi build on Windows
       - pixi build will allow to have source dependencies
       - Wilson to check

#### STACK-OF-TASKS/EIGENPY

- [#603 Update pixi.toml](https://github.com/stack-of-tasks/eigenpy/pull/603)
   - Created 12 days ago, updated 3 days ago, no status
       - same as above
       - Wilson to check

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 411 days ago, updated 61 days ago, status to review
- [#2779 Fix Eigen5 support on Pinocchio 3](https://github.com/stack-of-tasks/pinocchio/pull/2779)
   - Created 30 days ago, updated 12 days ago, no status
   - waiting for proxsuite on eigen5
- [#2793 Add color support for robot meshes in Viser](https://github.com/stack-of-tasks/pinocchio/pull/2793)
   - Created 17 days ago, updated 12 days ago, no status
   - no time yet, low priority
- [#2794 Update renamed dependency](https://github.com/stack-of-tasks/pinocchio/pull/2794)
   - Created 16 days ago, updated 11 days ago, no status
   - (can be closed - see previous week - fixed in pinocchio4)
- [#2797 Adding an ellipsoid joint to the joint collection](https://github.com/stack-of-tasks/pinocchio/pull/2797)
   - Created 10 days ago, updated 1 days ago, no status
   - Joris to review in the following weeks
- [#2799 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2799)
   - Created 2 days ago, updated 2 days ago, no status
   - Maintenance PR. all read because split in example-data-robot (split in 2 with loaders in separate project)
   - Need to explain to many people
   - will need to update all the projects that depend on thsi

#### SIMPLE-ROBOTICS/ALIGATOR

- [#369 Update pixi.toml for pixi 0.58.0](https://github.com/Simple-Robotics/aligator/pull/369)
   - Created 5 days ago, updated 4 days ago, no status
   - Joris to check
- [#370 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/370)
   - Created 2 days ago, updated 2 days ago, no status
   - Close (and do the manual fix in #369)

#### SIMPLE-ROBOTICS/PROXSUITE

- [#423 Add initial pixi support](https://github.com/Simple-Robotics/proxsuite/pull/423)
   - Created 27 days ago, updated 20 days ago, status to review
   - Need for the same PR (coal, eigenpy) to be merged to do the same here
- [#427 nix: add build with eigen 5, ref #426](https://github.com/Simple-Robotics/proxsuite/pull/427)
   - Created 6 days ago, updated 6 days ago, no status
   - Same error wrt eigen5 changes in random test (takes more time to converge)
   - Valgrind does not report anything
   - Lucas to check (later)
   - Ignore the tests for now so that Nix CI is green, so that can be merged (nix is mandatory)

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#776 Update pixi lockfile](https://github.com/coal-library/coal/pull/776)
   - Created 2 days ago, merged 1 days ago
- [#777 build(deps): bump prefix-dev/setup-pixi from 0.9.1 to 0.9.2](https://github.com/coal-library/coal/pull/777)
   - Created 1 days ago, merged 9 hours ago
- [#778 build(deps): bump astral-sh/setup-uv from 6 to 7](https://github.com/coal-library/coal/pull/778)
   - Created 1 days ago, merged 6 hours ago

#### STACK-OF-TASKS/EIGENPY

- [#604 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/604)
   - Created 2 days ago, merged 1 days ago
- [#605 build(deps): bump astral-sh/setup-uv from 6 to 7](https://github.com/stack-of-tasks/eigenpy/pull/605)
   - Created 1 days ago, merged 9 hours ago
- [#606 build(deps): bump prefix-dev/setup-pixi from 0.9.1 to 0.9.2](https://github.com/stack-of-tasks/eigenpy/pull/606)
   - Created 1 days ago, merged 8 hours ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#366 Introduce `mimalloc`-based memory resource](https://github.com/Simple-Robotics/aligator/pull/366)
   - Created 6 days ago, merged 6 days ago
- [#367 Integrate `mimalloc` memory resource as default resource for `SolverProxDDP`, move `blk-matrix.hpp` header to `aligator/core`](https://github.com/Simple-Robotics/aligator/pull/367)
   - Created 6 days ago, merged 5 days ago
- [#368 (Finally) remove deprecated `StageConstraint` template class](https://github.com/Simple-Robotics/aligator/pull/368)
   - Created 5 days ago, merged 5 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#428 build(deps): bump actions/download-artifact from 5 to 6](https://github.com/Simple-Robotics/proxsuite/pull/428)
   - Created 1 days ago, merged 1 days ago
- [#429 build(deps): bump actions/upload-artifact from 4 to 5](https://github.com/Simple-Robotics/proxsuite/pull/429)
   - Created 1 days ago, merged 8 hours ago


## 2025-10-27

### News

No news this week

### Technical discussions

- [name=Wilson] No news yet on the Eigen5 feedstock PR (https://github.com/conda-forge/eigen-feedstock/pulls/49)
     - to be able to tag the ABI versions
 - [name=Joris Vaillant] Do we add new joint (spline, ellipsoid) to the default joint collection ?
     - what's the goal of the collection ? Only the joints in robotics or all ?
     - impact on HPP ?
         - some thongs are hardcoded - check if using a custom list of joints or the one in Pinocchio
     - check with Justin 
 - [name=Guilhem Saurel] pycppad
     - pycppad had automatic PR not merged
     - should we had the project in the meeting's agenda
         - not a major project advertized as Maestro stack
         - Joris to check now this project also
         - project in maintenance mode, not much dev anymore
 - [name=Guilhem Saurel] coal: boost serialization
     - should we change to optional ?
     - some people that use Coal outside of robotics domain (e.g., gaming, cross-compilation)
         - if required then its a nogo
     - could be also useful wrt the refactoring of the jrl-cmake-module
     - in the current refactoring of proxsuite (for the new jrl-cmake-module) then we have components and dependency will be automatically set/notset - so if not required boos serialization not included
         - 2 targets proxsuite and proxsuite-serialization
         - what about Python binding ? (not yet) 
         - not a priority (fringe use, lots of things on the table already)

- [name=Wilson Jallet] new project pushed in September: [pymetabind](https://github.com/hudson-trading/pymetabind) - enables interop between C++/Python binding frameworks
        - open PRs on corresponding frameworks: [pybind11](https://github.com/pybind/pybind11/pull/5800), [nanobind](https://github.com/wjakob/nanobind/pull/1140). No Boost.Python PR open yet it seems
- [name=Wilson Jallet] Using mimalloc (https://github.com/microsoft/mimalloc) in Aligator
- No new issue on GH for the projects (Pinocchio, Simple, ...)


### PR to review

#### COAL-LIBRARY/COAL

- [#774 Update pixi.toml](https://github.com/coal-library/coal/pull/774)
   - Created 3 days ago, updated 3 days ago, no status
   - more than a simple update of the toml
   - minimal versions Python, ...
   - pixi build (fixed options - not as good as Conan but helps)
   - fix about testing the binding boost pyton on Windows
   - similar PRs are open on other repositories
   - remaining issue wrt clang version on windows

#### STACK-OF-TASKS/EIGENPY

- [#603 Update pixi.toml](https://github.com/stack-of-tasks/eigenpy/pull/603)
   - Created 5 days ago, updated 3 days ago, no status
   - same as above

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 404 days ago, updated 54 days ago, status to review
- [#2779 Fix Eigen5 support on Pinocchio 3](https://github.com/stack-of-tasks/pinocchio/pull/2779)
   - Created 23 days ago, updated 5 days ago, no status
   - New problems when activating casadi - fixed
   - can be merged even if not everything
   - add Python and eigen5 support on Nix
- [#2793 Add color support for robot meshes in Viser](https://github.com/stack-of-tasks/pinocchio/pull/2793)
   - Created 10 days ago, updated 5 days ago, no status
   - Joris to check (but low priority, maybe next week)
   - Alexy should resolve points which are indeed solved
- [#2794 Update renamed dependency](https://github.com/stack-of-tasks/pinocchio/pull/2794)
   - Created 9 days ago, updated 4 days ago, no status
   - Will be corrected in Pinocchio4
   - Can be closed
- [#2797 Adding an ellipsoid joint to the joint collection](https://github.com/stack-of-tasks/pinocchio/pull/2797)
   - Created 3 days ago, updated 15 hours ago, no status
   - Missing test on translation and FD test
   - Check dimensions given to data


#### SIMPLE-ROBOTICS/ALIGATOR

- [#365 Lie Group and Lie algebra redesign](https://github.com/Simple-Robotics/aligator/pull/365)
   - Created 3 days ago, updated 3 days ago, no status
   - Drafted work along with Yann
- [#366 Introduce mimalloc-based memory resource](https://github.com/Simple-Robotics/aligator/pull/366)
    - Drafted PR
    - Use [mimalloc](https://github.com/microsoft/mimalloc) from Microsoft


#### SIMPLE-ROBOTICS/PROXSUITE

- [#423 Add initial pixi support](https://github.com/Simple-Robotics/proxsuite/pull/423)
   - Created 20 days ago, updated 13 days ago, status to review
   - On pause (modernize pixi files first, then work on pixi support in ProxSuite)

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#772 Fix contact patches](https://github.com/coal-library/coal/pull/772)
   - Created 6 days ago, merged 6 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2786 Add names for joints inside a composite joint](https://github.com/stack-of-tasks/pinocchio/pull/2786)
   - Created 13 days ago, merged 6 days ago
- [#2795 build(deps): bump prefix-dev/setup-pixi from 0.9.1 to 0.9.2](https://github.com/stack-of-tasks/pinocchio/pull/2795)
   - Created 7 days ago, merged 5 days ago
- [#2796 bindings/python/visualizers : add overload for `BaseVisualizer::play()` in `VisualizerPythonVisitor`](https://github.com/stack-of-tasks/pinocchio/pull/2796)
   - Created 6 days ago, merged 5 days ago
   - For C++ visualizers

#### SIMPLE-ROBOTICS/ALIGATOR

- [#360 modelling : Fixes for upcoming changes to Pinocchio's API](https://github.com/Simple-Robotics/aligator/pull/360)
   - Created 6 days ago, merged 6 days ago
- [#362 [core] Move allocator/ArenaMatrix headers from `aligator/memory` to core](https://github.com/Simple-Robotics/aligator/pull/362)
   - Created 6 days ago, merged 6 days ago
- [#361 Introduce support for upcoming Pinocchio 4](https://github.com/Simple-Robotics/aligator/pull/361)
   - Created 6 days ago, merged 5 days ago
   - Forward support for Pinocchio4
- [#364 Extend support for `std::string_view` (C++ and Python)](https://github.com/Simple-Robotics/aligator/pull/364)
   - Created 3 days ago, merged 3 days ago
   - C++17 wrapper for `const char*`
   - use case : avoids string allocation when doing a lookup in a map

## 2025-10-20

### News

 - [name=Joris Vaillant] Aligator v0.16 release :tada:
     - removes old backend, heavy refactoring of main backend. Improves performances significantly (x3 on a Ricatti benchmark).
         - Some features have been removed (implicit integrator) but not used - need some work to reformulate.
         - Next steps : 0.17 with the new implicit integrator or directly 1.0 with computation graphs

### Technical discussions

 - [name=Joris Vaillant] Global migration to macos-15-intel
     - That will be the last Mac-Intel image supported on Github (only Mac-Arm later).
     - Also, Python 3.9 is discontinued (3.14 to add)
 - [name=Guilhem Saurel] pinocchio-minimal
     - Project in SoT. Minimal example to use CMake. Used extensively in the CI.
     - 2 news issues on this project (one wrt naming, one on using this as a template)
         - template: improve the doc instead ("Getting Started")

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2792 [Feature]: Colors of robots are not fully applied in Viser](https://github.com/stack-of-tasks/pinocchio/issues/2792)
       - Joris to check this week
       - Rerun not good enough for robotics (more a player than an interactive viewer). Rerun has evaolved this summer. Checl again ?
       - Ongoing work with Viser in LAAS
       - What about Candlewick ? more a renderer than a viewer

#### simple-robotics/nanoeigenpy

 - Items to discuss:
   - [#23 CMake: use of `Python_SITELIB`](https://github.com/Simple-Robotics/nanoeigenpy/issues/23)
       - Currently in nix, patch to address this, but many messages wrt this issue on ROS CI
       - Disable ROS CI for now until refactoring of v2 CMake tools
           - add macro to get relative path of sitelib
       - Allow overide for Windows (relative solution does not work)

### PR to review

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 397 days ago, updated 47 days ago, status to review
- [#2779 Fix Eigen5 support on Pinocchio 3](https://github.com/stack-of-tasks/pinocchio/pull/2779)
   - Created 16 days ago, updated 3 days ago, no status
       - CI test fails, Joris to check
- [#2786 Add names for joints inside a composite joint](https://github.com/stack-of-tasks/pinocchio/pull/2786)
   - Created 6 days ago, updated 2 days ago, no status
- [#2793 Add color support for robot meshes in Viser](https://github.com/stack-of-tasks/pinocchio/pull/2793)
   - Created 3 days ago, updated 2 days ago, no status
       - checks by Guilhem already, Joris to check and merge
- [#2794 Update renamed dependency](https://github.com/stack-of-tasks/pinocchio/pull/2794)
   - Created 2 days ago, updated 2 days ago, no status
   - waiting for Pinocchio4
   - Need collision option on by default ?
       - yes, for pinocchio4
- [#2795 build(deps): bump prefix-dev/setup-pixi from 0.9.1 to 0.9.2](https://github.com/stack-of-tasks/pinocchio/pull/2795)
   - Created 6 hours ago, updated 6 hours ago, no status

#### SIMPLE-ROBOTICS/PROXSUITE

- [#415 [WIP]: Implementation of OSQP algorithm in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 58 days ago, updated 17 days ago, no status
   - Move as WIP, ongoing work
- [#423 Add initial pixi support](https://github.com/Simple-Robotics/proxsuite/pull/423)
   - Created 13 days ago, updated 6 days ago, status to review
   - Joris to review this week

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#768 Migrate to macos-15-intel](https://github.com/coal-library/coal/pull/768)
   - Created 4 days ago, merged 4 days ago
- [#769 ROS: update](https://github.com/coal-library/coal/pull/769)
   - Created 4 days ago, merged 4 days ago
- [#770 CMake: lib version/soversion](https://github.com/coal-library/coal/pull/770)
   - Created 4 days ago, merged 3 days ago
   - Only major version now.

#### STACK-OF-TASKS/EIGENPY

- [#601 Migrate to macos-intel-15](https://github.com/stack-of-tasks/eigenpy/pull/601)
   - Created 6 days ago, merged 4 days ago
- [#602 ROS: update](https://github.com/stack-of-tasks/eigenpy/pull/602)
   - Created 4 days ago, merged 4 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2785 build(deps): bump astral-sh/setup-uv from 6 to 7](https://github.com/stack-of-tasks/pinocchio/pull/2785)
   - Created 7 days ago, merged 6 days ago
- [#2788 Migrate to macos-15-intel](https://github.com/stack-of-tasks/pinocchio/pull/2788)
   - Created 4 days ago, merged 4 days ago
- [#2791 CMake: no need for boost system](https://github.com/stack-of-tasks/pinocchio/pull/2791)
   - Created 4 days ago, merged 3 days ago
- [#2789 ROS: update](https://github.com/stack-of-tasks/pinocchio/pull/2789)
   - Created 4 days ago, merged 3 days ago
- [#2777 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2777)
   - Created 19 days ago, merged 2 days ago
   - On Windows, CI fails when building with all options (takes too long). Disabled for now. To investigate.
- [#2790 CMake: updates for CMake >= 3.22](https://github.com/stack-of-tasks/pinocchio/pull/2790)
   - Created 4 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#351 flake.nix : add catch2 dep](https://github.com/Simple-Robotics/aligator/pull/351)
   - Created 6 days ago, merged 6 days ago
- [#352 Update CHANGELOG.md following changes merged in #348](https://github.com/Simple-Robotics/aligator/pull/352)
   - Created 6 days ago, merged 6 days ago
- [#353 gh-pages workflow : use pixi](https://github.com/Simple-Robotics/aligator/pull/353)
   - Created 6 days ago, merged 6 days ago
- [#354 pixi : add doc feature and task, use in gh-pages workflow](https://github.com/Simple-Robotics/aligator/pull/354)
   - Created 6 days ago, merged 6 days ago
- [#355 Remove fmt dependency max version spec](https://github.com/Simple-Robotics/aligator/pull/355)
   - Created 5 days ago, merged 5 days ago
- [#357 Migrate to macos-15-intel](https://github.com/Simple-Robotics/aligator/pull/357)
   - Created 4 days ago, merged 4 days ago
- [#358 Add new-version environment](https://github.com/Simple-Robotics/aligator/pull/358)
   - Created 4 days ago, merged 4 days ago
- [#359 `CostStack` - add weight getter and setters (and increase minimum eigenpy version)](https://github.com/Simple-Robotics/aligator/pull/359)
   - Created 2 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#425 Migrate to macos-15-intel](https://github.com/Simple-Robotics/proxsuite/pull/425)
   - Created 2 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#24 Migrate to macos-15-intel](https://github.com/Simple-Robotics/nanoeigenpy/pull/24)
   - Created 4 days ago, merged 4 days ago

## 2025-10-13

### News

 - [name=Pierre-Guillaume] Preparation prestation pour documentation (infra et utilisateur)
     - nouvelle procedure TIRREX : vise à présenter à l'ensemble des responsables d'axes

### Technical discussions

 - [name=Ghuilem] Add the new jrl-cmake-module project in the agenda

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2782 [Bug]: Fixed joint in mujoco as first joint does not take body position into account](https://github.com/stack-of-tasks/pinocchio/issues/2782)
       - check if bug still there in Pinocchio4
       - either fix in Pinocchio3 or use model graphs (Pinocchio4 only)
   - [#2778 Support for Arch Linux (eigen 5)?](https://github.com/stack-of-tasks/pinocchio/issues/2778]
       - Guilhem answered, one last thing to be done but issue is solved


### PR to review

#### COAL-LIBRARY/COAL

- [#767 flake.lock: Update](https://github.com/coal-library/coal/pull/767)
   - Created 19 hours ago, updated 19 hours ago, no status
   - CI Nix disapproves, to be closed: Guilhem is currently working on it

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 390 days ago, updated 40 days ago, status to review
- [#2777 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2777)
   - Created 12 days ago, updated 4 days ago, no status
   - issues with pixi build (max size reached)
   - fix to remove unused files in the github action
       - scripts to remove unused features like docker, ...
       - run_with_debinfo -> no assert messages
   - also remaining bug wrt missing scipy on arm (use ssh on runner to investigate - slow to build on qemu)
- [#2779 Fix Eigen5 support on Pinocchio 3](https://github.com/stack-of-tasks/pinocchio/pull/2779)
   - Created 9 days ago, updated 9 days ago, no status
   - Guilhem will take a look
- [#2784 Adding a spline joint to the joint collection](https://github.com/stack-of-tasks/pinocchio/pull/2784)
   - Created 2 days ago, updated 2 days ago, no status
   - drafted PR, therefore marked as wip
- [#2785 build(deps): bump astral-sh/setup-uv from 6 to 7](https://github.com/stack-of-tasks/pinocchio/pull/2785)
   - Created 6 hours ago, updated 6 hours ago, no status
   - merged


#### SIMPLE-ROBOTICS/PROXSUITE

- [#415 [WIP]: Implementation of OSQP algorithm in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 51 days ago, updated 10 days ago, no status
   - drafted PR: profiling to come
- [#423 Add initial pixi support](https://github.com/Simple-Robotics/proxsuite/pull/423)
   - Created 6 days ago, updated 6 days ago, no status
   - lockfile missing


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#766 [pre-commit.ci] pre-commit autoupdate](https://github.com/coal-library/coal/pull/766)
   - Created 6 days ago, merged 5 days ago
   - Update of clang-format, changes the stylr (massive changes wrt space)
   - Issues wrt merge conflicts

#### STACK-OF-TASKS/EIGENPY

- [#600 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/eigenpy/pull/600)
   - Created 6 days ago, merged 6 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2781 build(deps): bump actions/attest-build-provenance from 2 to 3](https://github.com/stack-of-tasks/pinocchio/pull/2781)
   - Created 7 days ago, merged 6 days ago
- [#2780 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2780)
   - Created 8 days ago, merged 6 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#347 CMake: BUILD_STANDALONE_PYTHON_INTERFACE](https://github.com/Simple-Robotics/aligator/pull/347)
   - Created 6 days ago, merged 6 days ago
   - Split the binding of the main lib and the python bindingd
- [#349 Refactor/algo changes: reorient around explicit dynamics](https://github.com/Simple-Robotics/aligator/pull/349)
   - Created 6 days ago, merged 5 days ago
- [#348 Revamp ProxDDP solver : remove proximal iteration over co-state, temporarily remove implicit dynamics](https://github.com/Simple-Robotics/aligator/pull/348)
   - Created 6 days ago, merged 2 days ago
   - #349 merged into this PR
   - performance improvments (reduce complexity)
        - fix memory pull
        - computation graph

#### SIMPLE-ROBOTICS/PROXSUITE

- [#422 build(deps): bump actions/setup-python from 5 to 6](https://github.com/Simple-Robotics/proxsuite/pull/422)
   - Created 11 days ago, merged 6 days ago
- [#424 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/proxsuite/pull/424)
   - Created 6 days ago, merged 5 days ago

## 2025-10-06

### News

 - [name=Guilhem Saurel] release COAL 3.0.2 JRL CMake module, TSID Croccodyl. To come: Aligator
     - source, nix a venir ainsi que ROS
     - reste pipy et robotpkg
     - support des nouvelles versions de CMake, split du packaging entre c++ et bindings python
 - [name=Joris Vaillant] release de Eigen 5.0
     - faut-il garder les CI qui n'ont pas de lockfile ? (archlinux)
         - garder la CI mais ne pas la rendre obligatoire ? (canari)
         - les faire plutot offiline 1 fois par mois (et pas sur les PR)
             - ok

### Technical discussions

 - [name=Joris Vaillant] jrl-cmake-modules 2 on a dedicated repository or on a new branch ?
     - pas/peu de point communs entre les deux projets a priori
     - plus d'implication des JRL egalement
     - par contre rester dans le meme repo evite de refaire le packaging
     - attendre d'avoir une premiere version pour voir ce que ca donne
     - repartir sur une base saine - POC deja bien avancée, comparer avec jrl-cmake-module v1 pour voir ce qui est a garder ou pas. Evaluer ce qui est utile pour les projets dependants de jrl-cmake-modules
     - licence des fichiers jrl-cmake-modules à revérifier (éviter les GPL-3 ou autres licences problématiques)
         - verifier les auteurs, l'utilite des finders avec d'autres licences que BSD

 
#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2778 Support for Arch Linux (eigen 5)?](https://github.com/stack-of-tasks/pinocchio/issues/2778)
       - ne pas ajouter de CI Arch Linux
       - job eigen 5 pour rebuild l pinocchio sans dépendances
       - pour l'instant garder eigen 3 et eigen 5
   - [#2775 Push Pinocchio 3.8.0 to all active ROS releases?](https://github.com/stack-of-tasks/pinocchio/issues/2775)
       - no gain of time and an issue of security in the ROS distribution
       - suggest to contribute on similar topics
       - contact for official consortium relationship

### PR to review

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 383 days ago, updated 33 days ago, status to review
- [#2777 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2777)
   - Created 5 days ago, updated 4 days ago, no status
   - issue with GH runners - since a few weeks - error messages are too short
- [#2779 Fix Eigen5 support on Pinocchio 3](https://github.com/stack-of-tasks/pinocchio/pull/2779)
   - Created 2 days ago, updated 2 days ago, no status
   - Removed `EIGEN_CONSTEXPR` (already done in Pinocchio 4)
   - Guilhem to add support for Eigen5 (not urgent)
- [#2780 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2780)
   - Created 1 days ago, updated 1 days ago, no status
- [#2781 build(deps): bump actions/attest-build-provenance from 2 to 3](https://github.com/stack-of-tasks/pinocchio/pull/2781)
   - Created 6 hours ago, updated 6 hours ago, no status

#### SIMPLE-ROBOTICS/PROXSUITE

- [#415 [WIP]: Implementation of OSQP algorithm in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 44 days ago, updated 3 days ago, no status
   - Some profiling to do.
- [#422 build(deps): bump actions/setup-python from 5 to 6](https://github.com/Simple-Robotics/proxsuite/pull/422)
   - Created 4 days ago, updated 4 days ago, no status
   - ArchLinux fails, but not relevant. Merged.

#### SIMPLE-ROBOTICS/ALIGATOR

- [#347 CMake: BUILD_STANDALONE_PYTHON_INTERFACE](https://github.com/Simple-Robotics/aligator/pull/347)
    - Joris to check access for Guilhem wrt this repository 

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#757 Release/3.0.2](https://github.com/coal-library/coal/pull/757)
   - Created 11 days ago, merged 6 days ago
   - Split of python bindings, update docker generation
- [#759 Update pixi lockfile](https://github.com/coal-library/coal/pull/759)
   - Created 5 days ago, merged 4 days ago
- [#765 Fix compilation warning for DistanceRequest](https://github.com/coal-library/coal/pull/765)
   - Created 4 days ago, merged 3 days ago
   - Removed warnings deprecated
- [#764 build(deps): bump actions/attest-build-provenance from 2 to 3](https://github.com/coal-library/coal/pull/764)
   - Created 4 days ago, merged 3 days ago
- [#763 build(deps): bump actions/checkout from 4 to 5](https://github.com/coal-library/coal/pull/763)
   - Created 4 days ago, merged 2 days ago
- [#762 build(deps): bump actions/setup-python from 5 to 6](https://github.com/coal-library/coal/pull/762)
   - Created 4 days ago, merged 2 days ago
- [#761 build(deps): bump prefix-dev/setup-pixi from 0.9.0 to 0.9.1](https://github.com/coal-library/coal/pull/761)
   - Created 4 days ago, merged 2 days ago
- [#760 build(deps): bump ros-industrial/industrial_ci from e3d16c224caf4832cf68e74093eb70f3a979b4cc to eb3ea328ff056aa2435d5b3493e7e2929c310f8e](https://github.com/coal-library/coal/pull/760)
   - Created 4 days ago, merged 1 days ago

#### STACK-OF-TASKS/EIGENPY

- [#594 Refactorize recent code change](https://github.com/stack-of-tasks/eigenpy/pull/594)
   - Created 7 days ago, merged 5 days ago
- [#597 build(deps): bump ros-industrial/industrial_ci from e3d16c224caf4832cf68e74093eb70f3a979b4cc to eb3ea328ff056aa2435d5b3493e7e2929c310f8e](https://github.com/stack-of-tasks/eigenpy/pull/597)
   - Created 4 days ago, merged 3 days ago
- [#595 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/595)
   - Created 5 days ago, merged 3 days ago
- [#598 build(deps): bump prefix-dev/setup-pixi from 0.9.0 to 0.9.1](https://github.com/stack-of-tasks/eigenpy/pull/598)
   - Created 4 days ago, merged 2 days ago
- [#596 Fix compilation issues related to Eigen 5](https://github.com/stack-of-tasks/eigenpy/pull/596)
   - Created 4 days ago, merged 2 days ago
- [#599 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/599)
   - Created 2 days ago, merged 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2774 build(deps): bump prefix-dev/setup-pixi from 0.9.0 to 0.9.1](https://github.com/stack-of-tasks/pinocchio/pull/2774)
   - Created 7 days ago, merged 6 days ago
- [#2776 setup dockgen](https://github.com/stack-of-tasks/pinocchio/pull/2776)
   - Created 6 days ago, merged 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#342 Nix CI: updates](https://github.com/Simple-Robotics/aligator/pull/342)
   - Created 7 days ago, merged 6 days ago
- [#345 Simplify solver backend: remove CHOLMOD](https://github.com/Simple-Robotics/aligator/pull/345)
   - Created 6 days ago, merged 6 days ago
- [#346 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/346)
   - Created 5 days ago, merged 4 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 62 days ago, merged 6 days ago

## 2025-09-29

### News

 - [name=Antoine Hoarau] Rewrite of proxsuite's CMake in progress.
 - Sarah shortly presented the [Faer project](https://faer.veganb.tw/), a linear algebra library in Rust
 - [name=Wilson Jallet] Eigen 5 should be out tomorrow a 9am. Issue with force-push of tags.
     - issues with 5.0.0 - TU that work on linux but not mac. 

### Technical discussions

- [name=justin] preparing for Pinocchio 4 - ongoing discussion on minimal roadmap

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2768 Bug Report: `pinocchio::log6` fails with NaN](https://github.com/stack-of-tasks/pinocchio/issues/2768)
       - issue with pathological cas wrt acos. Proposed fix not working for autodiff.
       - Assigned to Yann

### PR to review

#### COAL-LIBRARY/COAL

- [#757 Release/3.0.2](https://github.com/coal-library/coal/pull/757)
   - Created 4 days ago, updated 4 days ago, no status
   - PR with packaging related commits
   - Remain todo : apply to Aligator
- [#758 Optimize the linear and log convex shape support function](https://github.com/coal-library/coal/pull/758)
   - Created 3 days ago, updated 2 days ago, no status
   - back to wip since remaining todo

#### STACK-OF-TASKS/EIGENPY

- [#594 Refactorize recent code change](https://github.com/stack-of-tasks/eigenpy/pull/594)
   - Created 22 hours ago, updated 15 hours ago, no status
   - Joris to review

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 376 days ago, updated 26 days ago, status to review
- [#2774 build(deps): bump prefix-dev/setup-pixi from 0.9.0 to 0.9.1](https://github.com/stack-of-tasks/pinocchio/pull/2774)
   - Created 6 hours ago, updated 6 hours ago, no status

#### SIMPLE-ROBOTICS/ALIGATOR

- [#342 Nix CI: updates](https://github.com/Simple-Robotics/aligator/pull/342)
   - Created 14 hours ago, updated 13 hours ago, no status
   - Missing CI, added by Guilhem

#### SIMPLE-ROBOTICS/PROXSUITE

- [#415 [WIP]: Implementation of OSQP algorithm in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 37 days ago, updated 4 days ago, no status
   - Some TU fail, need to check API break

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 55 days ago, updated 31 days ago, no status

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#737 dockgen: init](https://github.com/coal-library/coal/pull/737)
   - Created 62 days ago, merged 6 days ago

#### STACK-OF-TASKS/EIGENPY

- [#590 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/590)
   - Created 25 days ago, merged 6 days ago
- [#593 Remove `accelerate.hpp`](https://github.com/stack-of-tasks/eigenpy/pull/593)
   - Created 4 days ago, merged 4 days ago
- [#592 Add support for Python slice objects for `std::vector`](https://github.com/stack-of-tasks/eigenpy/pull/592)
   - Created 5 days ago, merged 3 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2767 build(deps): bump actions/checkout from 4 to 5](https://github.com/stack-of-tasks/pinocchio/pull/2767)
   - Created 7 days ago, merged 6 days ago
- [#2755 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2755)
   - Created 24 days ago, merged 6 days ago
- [#2771 example-viser-viewer: fix erd path](https://github.com/stack-of-tasks/pinocchio/pull/2771)
   - Created 1 days ago, merged 1 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#339 cmake : sync submodule](https://github.com/Simple-Robotics/aligator/pull/339)
   - Created 4 days ago, merged 4 days ago
- [#340 [gar] Add CTAD for parallel and sequential solvers](https://github.com/Simple-Robotics/aligator/pull/340)
   - Created 2 days ago, merged 2 days ago
- [#343 README: fix names in bibtex](https://github.com/Simple-Robotics/aligator/pull/343)
   - Created 13 hours ago, merged 13 hours ago
- [#344 fix compat with crocoddyl v3.1.0](https://github.com/Simple-Robotics/aligator/pull/344)
   - Created 13 hours ago, merged 13 hours ago

## 2025-09-22

### News
 - [name=Pierre-Guillaume] Technical work on the PUMA will start soon. Upcoming meeting to discuss planning jrl-cmake-module
 - [name=Joris Vaillant] Pinocchio 3.8 release
     - split of c++/pythAdd pinocchio::graph::ModelGraph class on bindings
     - still need Boost (primarily for variants) - boost variant 2 for pinocchio 4
     - model graphs (helps in code factorisation)
     - bug fixes

### Technical discussions

- [name=Guilhem Saurel] release process
    - should discuss on release process - check that the whole stack still works before doing a release.
        - document on release (pinocchio)
        - can we automatize (check existing script)
        - parts of the release process in jrl-cmake-module that could be pushed in the CI?
- [name=Guilhem Saurel] git bisect
    - to use git bisect, should ensure all commits are ok. regression tests vs bisect.
        - squashing? maybe since not possible to ensure that all commits are fine.
        - possible to have bisect only consider merge commits? (alternative to squash)
            - hard to track the commits where ci works
            - hard to enforce all commits are fine wrt CI
- [name=Guilhem Saurel] split packaging for Coal ?
    - current state of Coal is not suitable for release with split packaging C++/Python
    - do this with the previous release ? (not the preferred behavior as maintenance fix on previous release should stay on release branch, current state prevents release soon, 1 or 2 months ? ok with this approach then)

#### stack-of-tasks/tsid

- [name=Etienne Arlaud] Small release (PR solved a segfault)
    - After the split libtsid and python binding will be made and merged

#### coal-library/coal

 - Items to discuss:
   - [#755 BVHModel security_margin check error](https://github.com/coal-library/coal/issues/755)

### PR to review

#### STACK-OF-TASKS/EIGENPY

- [#590 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/590)
   - Created 15 days ago, updated 15 days ago, no status
       - Guilhem to check

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 366 days ago, updated 16 days ago, status to review
- [#2755 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2755)
   - Created 14 days ago, updated 13 days ago, no status
       - Guilhem to check

#### SIMPLE-ROBOTICS/PROXSUITE

- [#414 Issues with pytorch bindings in the case where structural_feasibility=False.](https://github.com/Simple-Robotics/proxsuite/pull/414)
   - Created 41 days ago, updated 24 days ago, no status
       - Waiting for extra work from Mathis, moved to WIP status
- [#415 [WIP]: Add OSQP solver in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 27 days ago, updated 3 days ago, no status
       - Need to do some profiling
       - General issue with missing initialisation (introduced at some point in ProxSuite - reported by valgrind).
       - Difference comparing algo and implementaiton (2 different things)
           - ProxQP vs OSQP
       - Potential breaking changes

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 45 days ago, updated 21 days ago, no status
       - Guilhem to rebase/merge

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#754 flake.lock: Update](https://github.com/coal-library/coal/pull/754)
   - Created 6 days ago, merged 6 days ago
- [#756 Don't trigger CI on push and pull_request event](https://github.com/coal-library/coal/pull/756)
   - Created 1 days ago, merged 1 days ago

#### STACK-OF-TASKS/EIGENPY

- [#591 Don't trigger CI on push and pull_request event](https://github.com/stack-of-tasks/eigenpy/pull/591)
   - Created 8 days ago, merged 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2762 build(deps): bump ros-industrial/industrial_ci from e3d16c224caf4832cf68e74093eb70f3a979b4cc to eb3ea328ff056aa2435d5b3493e7e2929c310f8e](https://github.com/stack-of-tasks/pinocchio/pull/2762)
   - Created 4 days ago, merged 3 days ago
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 86 days ago, merged 2 days ago
- [#2763 Fix axis of unaligned mimic joint](https://github.com/stack-of-tasks/pinocchio/pull/2763)
   - Created 2 days ago, merged 1 days ago
- [#2765 Don't trigger CI on push and pull_request event #756](https://github.com/stack-of-tasks/pinocchio/pull/2765)
   - Created 1 days ago, merged 1 days ago
- [#2743 Fix/cannot found casadi](https://github.com/stack-of-tasks/pinocchio/pull/2743)
   - Created 39 days ago, merged 1 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#338 Fix C++20 support](https://github.com/Simple-Robotics/aligator/pull/338)
   - Created 14 hours ago, merged 13 hours ago

### PR merged within PREVIOUS WEEK (no meeting)

#### COAL-LIBRARY/COAL

- [#753 Fix sqrDistLowerBound in octree traversal with height field](https://github.com/coal-library/coal/pull/753)
   - Created 7 days ago, merged 5 days ago
- [#754 flake.lock: Update](https://github.com/coal-library/coal/pull/754)
   - Created 2 days ago, merged 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2756 Add continuous joint as mimic in urdf parser](https://github.com/stack-of-tasks/pinocchio/pull/2756)
   - Created 9 days ago, merged 6 days ago
- [#2758 build(deps): bump actions/github-script from 7 to 8](https://github.com/stack-of-tasks/pinocchio/pull/2758)
   - Created 7 days ago, merged 6 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#331 Add a Python test for MPC-like iteration](https://github.com/Simple-Robotics/aligator/pull/331)
   - Created 93 days ago, merged 6 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#418 Upgrade nanobind to v2.9.2](https://github.com/Simple-Robotics/proxsuite/pull/418)
   - Created 6 days ago, merged 6 days ago
- [#419 Use nanobind's new recursive stub generation, fix dynamic module handling](https://github.com/Simple-Robotics/proxsuite/pull/419)
   - Created 6 days ago, merged 5 days ago
- [#421 ci : only trigger workflows on push when on devel](https://github.com/Simple-Robotics/proxsuite/pull/421)
   - Created 5 days ago, merged 5 days ago
- [#420 [veg] Fix `-Wdeprecated-literal-operator` warning](https://github.com/Simple-Robotics/proxsuite/pull/420)
   - Created 5 days ago, merged 4 days ago
- [#417 build(deps): bump actions/download-artifact from 4 to 5](https://github.com/Simple-Robotics/proxsuite/pull/417)
   - Created 12 days ago, merged 4 days ago
- [#416 build(deps): bump actions/checkout from 4 to 5](https://github.com/Simple-Robotics/proxsuite/pull/416)
   - Created 12 days ago, merged 4 days ago


# 2025-09-08

### News

 - [name=Pierre-Guillaume] Soumission projet "Concerto" pour AMI Robotique (industrialisation des logiciels, pilotes industriels, documentation)

### Technical discussions

 - [name=Wilson] Eigen 5.0 not really next door (nothing has been decided so far, no communication from maintainers). Need new people on eigen side that have time.

#### coal-library/coal

 - Items to discuss:
   - [#751 Whether using Security_margin increases performance](https://github.com/coal-library/coal/issues/751)
       - Putting 1 as security margin in the API increase the margin for detecting the collision, so normal 
       - Willson to answer, maybe with Louis

#### stack-of-tasks/eigenpy

 - Items to discuss:
   - [#586 Eigen 5.0 release next door](https://github.com/stack-of-tasks/eigenpy/issues/586)

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2757 After loading the MJCF, q0 is inconsistent with the base_link position computed by forward kinematics](https://github.com/stack-of-tasks/pinocchio/issues/2757)
       - Megan is handling the issue.
   - [#2753 [Bug]: Potential issue parsing mimic joints if they are continuous joints?](https://github.com/stack-of-tasks/pinocchio/issues/2753)
       - Ongoing PR will fix the issue

### PR to review

#### COAL-LIBRARY/COAL

- [#753 Fix sqrDistLowerBound in octree traversal with height field](https://github.com/coal-library/coal/pull/753)
   - Created 3 hours ago, updated 3 hours ago, no status
   - Puts a lowerbound on a computation but no description in the PR
   - Louis to check

#### STACK-OF-TASKS/EIGENPY

- [#590 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/590)
   - Created 4 days ago, updated 4 days ago, no status
   - Errors in the CI, Guilhem to check

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 355 days ago, updated 5 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 75 days ago, updated 12 days ago, no status
   - Waiting for Guilhem to merge.
- [#2743 Fix/cannot found casadi](https://github.com/stack-of-tasks/pinocchio/pull/2743)
   - Created 28 days ago, updated 12 days ago, no status
   - No response from contributor (issue with fix on the wrong branch). Joris to handle/fix this week and merge.
- [#2755 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2755)
   - Created 3 days ago, updated 2 days ago, no status
   - Waiting for Guilhem to merge.
- [#2756 Add continuous joint as mimic in urdf parser](https://github.com/stack-of-tasks/pinocchio/pull/2756)
   - Created 2 days ago, updated 2 days ago, no status
   - Potential issue with URDF parsing wrt Pinocchio4, to monitor. Cannot wait for Pinocchio4
- [#2758 build(deps): bump actions/github-script from 7 to 8](https://github.com/stack-of-tasks/pinocchio/pull/2758)
   - Created 6 hours ago, updated 6 hours ago, no status
   - Wait for previous PR to be merged

#### SIMPLE-ROBOTICS/PROXSUITE

- [#414 Issues with pytorch bindings in the case where structural_feasibility=False.](https://github.com/Simple-Robotics/proxsuite/pull/414)
   - Created 30 days ago, updated 13 days ago, no status
   - Waiting for Lucas
- [#415 [WIP]: Add OSQP solver in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 16 days ago, updated 2 days ago, no status
   - Waiting for Lucas
- [#416 build(deps): bump actions/checkout from 4 to 5](https://github.com/Simple-Robotics/proxsuite/pull/416)
   - Created 5 days ago, updated 5 days ago, no status
   - Issue on jrl-cmakemodules (version of cmake). 
- [#417 build(deps): bump actions/download-artifact from 4 to 5](https://github.com/Simple-Robotics/proxsuite/pull/417)
   - Created 5 days ago, updated 5 days ago, no status
   - Issue on jrl-cmakemodules (version of cmake). 

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 34 days ago, updated 10 days ago, no status
 
### PR merged within the week

#### COAL-LIBRARY/COAL

- [#747 Update pixi lockfile](https://github.com/coal-library/coal/pull/747)
   - Created 7 days ago, merged 6 days ago
- [#748 build(deps): bump actions/checkout from 4 to 5](https://github.com/coal-library/coal/pull/748)
   - Created 6 days ago, merged 6 days ago
- [#749 build(deps): bump prefix-dev/setup-pixi from 0.8.14 to 0.9.0](https://github.com/coal-library/coal/pull/749)
   - Created 6 days ago, merged 5 days ago
- [#750 Fix broadphase node collide bug](https://github.com/coal-library/coal/pull/750)
   - Created 5 days ago, merged 4 days ago
- [#746 Fix contact counting in octree collision detection with ShapeShapeCollide](https://github.com/coal-library/coal/pull/746)
   - Created 19 days ago, merged 3 days ago

#### STACK-OF-TASKS/EIGENPY

- [#585 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/585)
   - Created 7 days ago, merged 6 days ago
- [#587 build(deps): bump prefix-dev/setup-pixi from 0.8.14 to 0.9.0](https://github.com/stack-of-tasks/eigenpy/pull/587)
   - Created 5 days ago, merged 5 days ago
- [#588 build(deps): bump actions/checkout from 4 to 5](https://github.com/stack-of-tasks/eigenpy/pull/588)
   - Created 5 days ago, merged 4 days ago
- [#589 build(deps): bump actions/attest-build-provenance from 2 to 3](https://github.com/stack-of-tasks/eigenpy/pull/589)
   - Created 5 days ago, merged 4 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2750 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2750)
   - Created 7 days ago, merged 6 days ago
- [#2754 Add site attached to a fixed body in MJCF parser](https://github.com/stack-of-tasks/pinocchio/pull/2754)
   - Created 3 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#337 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/337)
   - Created 7 days ago, merged 6 days ago

## 2025-09-01

### News

 - [name=Pierre-Guillaume] Inria internal workshop on Software in Robotics (from an engineering point of view). About 25-30 engineers from the different campus will be in Paris Sept 15-17. Presentations from the team are expected.
 - [name=Joris] New release of eigenpy (3.12)
 - [name=Wilson] New releases of Candlewick (multiples)


### Technical discussions

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2747 [Bug]: sites not parsed as frames when attached to a fixed joint](https://github.com/stack-of-tasks/pinocchio/issues/2747)
       - problem with MJCF parser. 
       - Should test with Pinocchio4 as the parser has been heavily reworked. Should evaluate if fix for Pinocchio3 is necessary. 

### PR to review

#### COAL-LIBRARY/COAL

- [#742 Fix ContactPatchResult falling back to native exception for excessive…](https://github.com/coal-library/coal/pull/742)
   - Created 23 days ago, updated 18 days ago, no status
   - Fix for memory allocation error (better error message when asking for memory alloc beyond available memory). Check with Louis if better approach possible.
- [#746 Fix contact counting in octree collision detection with ShapeShapeCollide](https://github.com/coal-library/coal/pull/746)
   - Created 12 days ago, updated 48 minutes ago, no status
   - Louis to check.
- [#747 Update pixi lockfile](https://github.com/coal-library/coal/pull/747)
   - Created 56 minutes ago, updated 51 minutes ago, no status

#### STACK-OF-TASKS/EIGENPY

- [#585 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/585)
   - Created 1 hours ago, updated 1 hours ago, no status
   - Error on TU Windows. Also on other projects (to check).

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 348 days ago, updated 146 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 68 days ago, updated 5 days ago, no status
   - Waiting for consensus on the naming. To discuss with Justin.
- [#2743 Fix/cannot found casadi](https://github.com/stack-of-tasks/pinocchio/pull/2743)
   - Created 21 days ago, updated 5 days ago, no status
   - Fix in separate branch (git workflow issue). Wait for contributor's correction.
- [#2750 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2750)
   - Created 1 hours ago, updated 1 hours ago, no status
   - Issue with CI on Windows (same as other projects)

#### SIMPLE-ROBOTICS/ALIGATOR

- [#337 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/337)
   - Created 53 minutes ago, updated 53 minutes ago, no status

#### SIMPLE-ROBOTICS/PROXSUITE

- [#414 Issues with pytorch bindings in the case where structural_feasibility=False.](https://github.com/Simple-Robotics/proxsuite/pull/414)
   - Created 23 days ago, updated 6 days ago, no status
   - Waiting for Mathis feedback
- [#415 [WIP]: Add OSQP solver in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 9 days ago, updated 9 days ago, no status
   - Joris to review and fix the problem

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 27 days ago, updated 3 days ago, no status
   - Waiting for Guilhem / Nix

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#744 Remove useless boost components direct dependency](https://github.com/coal-library/coal/pull/744)
   - Created 19 days ago, merged 6 days ago
   - Problem with Boost target (on 189), but not used directly

#### STACK-OF-TASKS/PINOCCHIO

- [#2749 Fix copy of armature field in buildReducedModel](https://github.com/stack-of-tasks/pinocchio/pull/2749)
   - Created 9 days ago, merged 5 days ago
   - Added some TU
 
## 2025-08-25

### News

 - Creation of the Maestro consortium ongoing (administrative Inria process)

### Technical discussions

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2747 [Bug]: sites not parsed as frames when attached to a fixed joint](https://github.com/stack-of-tasks/pinocchio/issues/2747)
       - To be fixed as part of Pinocchio 4, as the Mujoco parser has evolved. Potential quickfix in the meantime to evuluate
   - [#2746 [Bug]: armature not carried over when using buildReducedModel](https://github.com/stack-of-tasks/pinocchio/issues/2746)
       - fixed, waiting for PR review

#### simple-robotics/aligator

 - Items to discuss:
   - [#336 Segmentation fault at runtime: Boost 1.86 incompatibility causes crash](https://github.com/Simple-Robotics/aligator/issues/336)
       - user possibly struggling in the compilation step (guess: both paths in LD_LIBRARYPATH). Ask confirmation that eigenpy coal also compiled with 1.86.

#### simple-robotics/simple

 - Items to discuss:
   - [#6 Regarding computation of dynamics and its derivaties for infeasible states](https://github.com/Simple-Robotics/Simple/issues/6)
       - question requiring detailed reply (definition of "*infeasible states*")

#### simple-robotics/candlewick

 - Items to discuss:
   - [#95 Investigate weird translucent effect on transparent objects](https://github.com/Simple-Robotics/candlewick/issues/95)
       - Await Wilson to get back

### PR to review

#### COAL-LIBRARY/COAL

- [#742 Fix ContactPatchResult falling back to native exception for excessive…](https://github.com/coal-library/coal/pull/742)
   - Created 16 days ago, updated 11 days ago, no status
   - check with Louis
- [#744 Remove useless boost components direct dependency](https://github.com/coal-library/coal/pull/744)
   - Created 12 days ago, updated 10 days ago, no status
   - can be merged
- [#746 Fix contact counting in octree collision detection with ShapeShapeCollide](https://github.com/coal-library/coal/pull/746)
   - Created 5 days ago, updated 4 days ago, no status
   - Justin to check

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 341 days ago, updated 139 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 61 days ago, updated 3 days ago, no status
   - Changing naming logic ? Avoid "duplicate" name ? No invert the name. Problem, already merged in jrl-cmakemodules and coal.
   - To discuss with Joris next week ? (technical discussion)
- [#2743 Fix/cannot found casadi](https://github.com/stack-of-tasks/pinocchio/pull/2743)
   - Created 14 days ago, updated 10 days ago, no status
   - wait for Joris
- [#2749 Fix copy of armature field in buildReducedModel](https://github.com/stack-of-tasks/pinocchio/pull/2749)
   - Created 2 days ago, updated 2 days ago, no status
   - Added Joris as reviewer

#### SIMPLE-ROBOTICS/PROXSUITE

- [#414 Issues with pytorch bindings in the case where structural_feasibility=False.](https://github.com/Simple-Robotics/proxsuite/pull/414)
   - Created 16 days ago, updated 16 days ago, no status
   - Fabian will check
   - Converted as draft for now
- [#415 [WIP]: Add OSQP solver in Proxsuite](https://github.com/Simple-Robotics/proxsuite/pull/415)
   - Created 2 days ago, updated 2 days ago, no status
       - drafted: Lucas is working on it

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 20 days ago, updated 10 days ago, no status
       - drafted: Nix CI is passing but wait for the commit to be merged in upstream branch

### PR merged within the week

#### STACK-OF-TASKS/PINOCCHIO

- [#2745 build(deps): bump actions/checkout from 4 to 5](https://github.com/stack-of-tasks/pinocchio/pull/2745)
   - Created 7 days ago, merged 4 days ago
- [#2744 build(deps): bump prefix-dev/setup-pixi from 0.8.14 to 0.9.0](https://github.com/stack-of-tasks/pinocchio/pull/2744)
   - Created 7 days ago, merged 4 days ago
- [#2748 Fix Viser visualizer loading DAE files as trimesh.Scene](https://github.com/stack-of-tasks/pinocchio/pull/2748)
   - Created 2 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#94 Add support for multisample anti-aliasing (MSAA), working HiDPI support](https://github.com/Simple-Robotics/candlewick/pull/94)
   - Created 5 days ago, merged 4 days ago
- [#96 core : Switch to `spdlog` for logging](https://github.com/Simple-Robotics/candlewick/pull/96)
   - Created 4 days ago, merged 4 days ago

## 2025-08-11

### Technical discussions

#### coal-library/coal

 - Items to discuss:
   - [#743 Build fails with upcoming Boost 1.89.0](https://github.com/coal-library/coal/issues/743)

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2740 Transforming of Jacobian / Jacobian Time Derivative Functionality](https://github.com/stack-of-tasks/pinocchio/issues/2740)

#### simple-robotics/simple

 - Items to discuss:
   - [#6 Regarding computation of dynamics and its derivaties for infeasible states](https://github.com/Simple-Robotics/Simple/issues/6)

#### simple-robotics/candlewick

 - Items to discuss:
   - [#91 Crash when saving video with missing or invalid file extension](https://github.com/Simple-Robotics/candlewick/issues/91)

### PR to review

#### COAL-LIBRARY/COAL

- [#741 Correctly calculate AABB for pruned octrees](https://github.com/coal-library/coal/pull/741)
   - Created 6 days ago, updated 3 days ago, no status
- [#742 Fix ContactPatchResult falling back to native exception for excessive…](https://github.com/coal-library/coal/pull/742)
   - Created 2 days ago, updated 2 days ago, no status

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 327 days ago, updated 125 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 47 days ago, updated 4 days ago, no status
- [#2743 Fix/cannot found casadi](https://github.com/stack-of-tasks/pinocchio/pull/2743)
   - Created 1 hours ago, updated 1 hours ago, no status

#### SIMPLE-ROBOTICS/PROXSUITE

- [#414 Issues with pytorch bindings in the case where structural_feasibility=False.](https://github.com/Simple-Robotics/proxsuite/pull/414)
   - Created 2 days ago, updated 2 days ago, no status

#### SIMPLE-ROBOTICS/NANOEIGENPY


- [#22 Nix: init](https://github.com/Simple-Robotics/nanoeigenpy/pull/22)
   - Created 6 days ago, updated 4 days ago, no status

### PR merged within the week

#### STACK-OF-TASKS/EIGENPY

- [#571 Linear algebra: Expose the remaining classes listed in Eigen documentation (decompositions and solvers)](https://github.com/stack-of-tasks/eigenpy/pull/571)
   - Created 37 days ago, merged 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2664 Introducing model graph](https://github.com/stack-of-tasks/pinocchio/pull/2664)
   - Created 107 days ago, merged 6 days ago
- [#2739 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2739)
   - Created 6 days ago, merged 4 days ago
- [#2741 Fix ViserVisualizer import without hppfcl](https://github.com/stack-of-tasks/pinocchio/pull/2741)
   - Created 4 days ago, merged 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#334 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/334)
   - Created 10 days ago, merged 6 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#413 replace `std::numeric_limits<T>::infinity()` by `max()`](https://github.com/Simple-Robotics/proxsuite/pull/413)
   - Created 12 days ago, merged 6 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#21 ROS: fix nanobind](https://github.com/Simple-Robotics/nanoeigenpy/pull/21)
   - Created 6 days ago, merged 4 days ago

## 2025-08-04

### News

### Technical discussions

 - [name=Guilhem] package names after split - Using similar convention for conda-forge ?(libcoal, coal-python)
     - proposal https://md.laas.fr/vlO8o5oMTI-SdXXpADNe0Q

#### simple-robotics/simple

 - Items to discuss:
   - [#5 No build/install instructions](https://github.com/Simple-Robotics/Simple/issues/5)
       - link to pin4 issue on the same topic
       - can be closed. pin it so that people can find it easily

#### simple-robotics/candlewick

 - Items to discuss:
   - [#91 Crash when saving video with missing or invalid file extension](https://github.com/Simple-Robotics/candlewick/issues/91)
       - internal issue. Wilson to check

### PR to review

#### COAL-LIBRARY/COAL

- [#737 dockgen: init](https://github.com/coal-library/coal/pull/737)
   - Created 6 days ago, updated 6 days ago, no status
   - similar to Proxsuite PR #408

#### STACK-OF-TASKS/EIGENPY

- [#571 Linear algebra: Expose the remaining classes listed in Eigen documentation (decompositions and solvers)](https://github.com/stack-of-tasks/eigenpy/pull/571)
   - Created 30 days ago, updated 9 days ago, no status
   - Some solvers are not returning a matrix. Possible to use a method in the binding to convert a view to a matrix to an actual matrix (if not possible in Eigen, then do nothing more)
   - wait for this PR to be merged before making a new release

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 320 days ago, updated 118 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 40 days ago, updated 26 days ago, no status
   - Joris to review this week
- [#2723 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/pinocchio/pull/2723)
   - Created 27 days ago, updated 26 days ago, no status
   - Still blocked due to reformeting of code

#### SIMPLE-ROBOTICS/ALIGATOR

- [#334 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/334)
   - Created 3 days ago, updated 3 days ago, no status
   - merged

#### SIMPLE-ROBOTICS/PROXSUITE

- [#413 replace `std::numeric_limits<T>::infinity()` by `max()`](https://github.com/Simple-Robotics/proxsuite/pull/413)
   - Created 5 days ago, updated 5 days ago, no status

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#738 Update pixi lockfile](https://github.com/coal-library/coal/pull/738)
   - Created 3 days ago, merged 2 days ago
- [#739 build(deps): bump cachix/cachix-action from 15 to 16](https://github.com/coal-library/coal/pull/739)
   - Created 2 days ago, merged 2 days ago
- [#740 build(deps): bump prefix-dev/setup-pixi from 0.8.10 to 0.8.14](https://github.com/coal-library/coal/pull/740)
   - Created 2 days ago, merged 2 days ago

#### STACK-OF-TASKS/EIGENPY

- [#583 build(deps): bump prefix-dev/setup-pixi from 0.8.10 to 0.8.14](https://github.com/stack-of-tasks/eigenpy/pull/583)
   - Created 2 days ago, merged 1 days ago
- [#581 README: Update my affiliation](https://github.com/stack-of-tasks/eigenpy/pull/581)
   - Created 9 days ago, merged 14 hours ago
- [#584 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/584)
   - Created 15 hours ago, merged 14 hours ago
- [#582 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/582)
   - Created 3 days ago, merged 11 hours ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2735 build(deps): bump prefix-dev/setup-pixi from 0.8.12 to 0.8.14](https://github.com/stack-of-tasks/pinocchio/pull/2735)
   - Created 7 days ago, merged 6 days ago
- [#2736 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2736)
   - Created 3 days ago, merged 2 days ago

## 2025-07-28

### News

 - [name=Pierre-Guillaume] PUMA under review

### Technical discussions


### PR to review

#### STACK-OF-TASKS/EIGENPY

- [#571 Linear algebra: Expose the remaining classes listed in Eigen documentation (decompositions and solvers)](https://github.com/stack-of-tasks/eigenpy/pull/571)
   - Created 23 days ago, updated 2 days ago, no status
   - Waiting for Joris to merge
- [#581 README: Update my affiliation](https://github.com/stack-of-tasks/eigenpy/pull/581)
   - Created 2 days ago, updated 2 days ago, no status
   - Waiting for Joris to merge

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 313 days ago, updated 111 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 33 days ago, updated 19 days ago, no status
   - a bit more work needed
- [#2723 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/pinocchio/pull/2723)
   - Created 20 days ago, updated 19 days ago, no status
- [#2735 build(deps): bump prefix-dev/setup-pixi from 0.8.12 to 0.8.14](https://github.com/stack-of-tasks/pinocchio/pull/2735)
   - Created 5 hours ago, updated 5 hours ago, no status

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#658 CMake: add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - Created 164 days ago, merged 3 days ago

#### STACK-OF-TASKS/EIGENPY

- [#575 dockgen: init](https://github.com/stack-of-tasks/eigenpy/pull/575)
   - Created 11 days ago, merged 5 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2734 Improve issue template and add PR template](https://github.com/stack-of-tasks/pinocchio/pull/2734)
   - Created 4 days ago, merged 4 days ago
- [#2728 CMake: allow use of system example-robot-data](https://github.com/stack-of-tasks/pinocchio/pull/2728)
   - Created 12 days ago, merged 3 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#13 Expose additional classes from Eigen (decompositions, solvers, geometry)](https://github.com/Simple-Robotics/nanoeigenpy/pull/13)
   - Created 19 days ago, merged 2 days ago
- [#20 Add list of contributors](https://github.com/Simple-Robotics/nanoeigenpy/pull/20)
   - Created 2 days ago, merged 2 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#37 Add Candlewick runtime (executable and client)](https://github.com/Simple-Robotics/candlewick/pull/37)
   - Created 108 days ago, merged 6 days ago
- [#90 multibody : allow reloading geometry models in `RobotScene` and `Visualizer`](https://github.com/Simple-Robotics/candlewick/pull/90)
   - Created 5 days ago, merged 5 days ago


## 2025-07-21

### News

 - [name=Pierre-Guillaume] CNRS PUMA submissions under review. Official announcement expected end of August (vacations)

### Technical discussions

 - [name=Joris] Remove codacy ?
     - ok for Python, but problematic for C++. Ruff would be better for Python? (potentially https://mypy-lang.org/ but pb with old code related/visualizer/meshcat/hpp-fcl, lack of typing)
     - Clang-tidy ? Lots of false positive in the pinocchio code base. Lot of work to setup the rules, and very slow (do only for diffs). Would certainly fail for metaprog/templates.
     - side subject: wrt visualizatio, check in Simple since newer code (Work in PUMA).
 - [name=Guilhem] docker
     - PR last week. Working on "official" docker image
         - https://github.com/stack-of-tasks/eigenpy/pull/575
         - dockgen : https://github.com/nim65s/dockgen
     - Will need to be merged, so that available for next release

#### stack-of-tasks/pinocchio

 - Items to discuss:
   - [#2729 Inverse/Forward Dynamics of a closed kinematic chain robot](https://github.com/stack-of-tasks/pinocchio/issues/2729)
       - Willson and Joris to discuss and answer
   - [#2726 how to get second derivative of the Jacobian with respect to the time.](https://github.com/stack-of-tasks/pinocchio/issues/2726)
       - Justin to answer
   - [#2725 End-effector wrench computed via inverse dynamics differs from BaseFeedback wrench？](https://github.com/stack-of-tasks/pinocchio/issues/2725)
       - Closed by user

### PR to review

#### STACK-OF-TASKS/EIGENPY

- [#571 Linear algebra: Expose the remaining classes listed in Eigen documentation (decompositions and solvers)](https://github.com/stack-of-tasks/eigenpy/pull/571)
   - Created 16 days ago, updated 7 hours ago, no status
   - Decomposition added
   - Some methods remain to be added
- [#575 dockgen: init](https://github.com/stack-of-tasks/eigenpy/pull/575)
   - Created 4 days ago, updated 3 days ago, no status

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 306 days ago, updated 104 days ago, status to review
   - waiting for pinocchio4
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 26 days ago, updated 12 days ago, no status
   - Tested by Guilhem. Joris and Guilhem to work this week to merge for Coal+Pinocchio ?
- [#2723 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/pinocchio/pull/2723)
   - Created 13 days ago, updated 12 days ago, no status
   - Blocked until Pinocchio4 due to code reformat
- [#2728 CMake: allow use of system example-robot-data](https://github.com/stack-of-tasks/pinocchio/pull/2728)
   - Created 5 days ago, updated 3 days ago, no status
   - Do a build all to test everything, can be reviewed then
   - In example robot data, PR to split packages is still in draft (need to agree on naming)
       - example-robot-data-scripts, example-robot-data-resources ?
       - breaking change wrt headers ? (e.g., for Croccodyl)

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#13 Expose additional classes from Eigen (decompositions, solvers, geometry)](https://github.com/Simple-Robotics/nanoeigenpy/pull/13)
   - Created 12 days ago, updated 7 hours ago, no status


#### SIMPLE-ROBOTICS/CANDLEWICK

- [#37 Add Candlewick runtime (executable and client)](https://github.com/Simple-Robotics/candlewick/pull/37)
   - Created 101 days ago, updated 5 days ago, status ready

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#733 sync submodule](https://github.com/coal-library/coal/pull/733)
   - Created 11 days ago, merged 3 days ago
- [#731 [pre-commit.ci] pre-commit autoupdate](https://github.com/coal-library/coal/pull/731)
   - Created 10 days ago, merged 9 days ago
- [#732 ROS: silent ci errors about nanoeigenpy for now](https://github.com/coal-library/coal/pull/732)
   - Created 9 days ago, merged 8 days ago

#### STACK-OF-TASKS/EIGENPY

- [#574 ROS: drop ROS1 & Python2 details](https://github.com/stack-of-tasks/eigenpy/pull/574)
   - Created 5 days ago, merged 4 days ago
- [#573 sync submodule](https://github.com/stack-of-tasks/eigenpy/pull/573)
   - Created 11 days ago, merged 3 days ago
- [#572 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/eigenpy/pull/572)
   - Created 10 days ago, merged 9 days ago

#### STACK-OF-TASKS/PINOCCHIO


- [#2727 build(deps): bump prefix-dev/setup-pixi from 0.8.10 to 0.8.11](https://github.com/stack-of-tasks/pinocchio/pull/2727)
   - Created 7 days ago, merged 5 days ago
- [#2716 Fix mimic patch for CRBA](https://github.com/stack-of-tasks/pinocchio/pull/2716)
   - Created 26 days ago, merged 5 days ago
- [#2730 Fixed explicit conversions to Scalar type in `log.hxx`](https://github.com/stack-of-tasks/pinocchio/pull/2730)
   - Created 4 days ago, merged 3 days ago
   - Potentially add a new TU ? to check
- [#2718 Beta version of Viser visualizer](https://github.com/stack-of-tasks/pinocchio/pull/2718)
   - Created 21 days ago, merged 3 days ago
   - As a general discussion, check the template for PRs
- [#2731 Fix missing argument in exposeDelassus() pybind definition](https://github.com/stack-of-tasks/pinocchio/pull/2731)
   - Created 3 days ago, merged 1 days ago
- [#2732 build(deps): bump prefix-dev/setup-pixi from 0.8.11 to 0.8.12](https://github.com/stack-of-tasks/pinocchio/pull/2732)
   - Created 5 hours ago, merged 1 hours ago
- [#2724 sync submodule](https://github.com/stack-of-tasks/pinocchio/pull/2724)
   - Created 8 days ago, merged 8 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#407 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/proxsuite/pull/407)
   - Created 10 days ago, merged 9 days ago
- [#408 Fix fetchcontent packaging](https://github.com/Simple-Robotics/proxsuite/pull/408)
   - Created 9 days ago, merged 8 days ago
- [#410 ci: Configure dependabot](https://github.com/Simple-Robotics/proxsuite/pull/410)
   - Created 8 days ago, merged 8 days ago
- [#409 sync submodule](https://github.com/Simple-Robotics/proxsuite/pull/409)
   - Created 8 days ago, merged 7 days ago
- [#412 build(deps): bump tarides/changelog-check-action from 2 to 3](https://github.com/Simple-Robotics/proxsuite/pull/412)
   - Created 8 days ago, merged 7 days ago
- [#411 build(deps): bump JamesIves/github-pages-deploy-action from 3.7.1 to 4.7.3](https://github.com/Simple-Robotics/proxsuite/pull/411)
   - Created 8 days ago, merged 7 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#333 sync submodule](https://github.com/Simple-Robotics/aligator/pull/333)
   - Created 11 days ago, merged 3 days ago


## 2025-07-07

### News

- [name=Pierre-Guillaume] "Depots APP" for early 2024 versions of Pinocchio (v2.7.1) and Aligator (v0.5) being finalized. More to be done in the coming weeks in preparation for kickstarting the Maestro consortium
- [name=Joris] Merged of nanobin du bindings nanobind de Coal
- [name=Justin] Deepmind/Nvidia/Disney co-developpent nvx simulateur (Warp and not Jax, backend detection collision based on Coal/GJK), Python framework, reimplements Mujoco. 
    - Response to genesis  (https://genesis-embodied-ai.github.io/) ?
    - implies that existing simulators from them will be dropped

### Technical discussions

- [name=Guilhem] standalone python
    - All tests completed. jrl-cmakemodules ok. PR to be merged soon.
    - Some tests last week by Joris for Coal, ok so fr but need more tests
    - Joris to look at PR for jrl, coal, pinocchio
        - priority for the jrl PR, blocking for ROS, Docker
- [name=Wilson] 1 month ago, PR on eigen
  - some work by reviewers, comments, still waiting
  - Deadline freeze for Ubuntu 26.04 ?
      - important/crucial to get Eigen 3.5 in it
  
### PR to review

#### STACK-OF-TASKS/EIGENPY

- [#571 Linear algebra: Expose the remaining Eigen classes (decompositions and solvers)](https://github.com/stack-of-tasks/eigenpy/pull/571)
   - Created 2 days ago, updated 2 days ago, no status
   - Some TU to finish, should be ready soon

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 292 days ago, updated 90 days ago, status to review
- [#2714 CMake:  add BUILD_STANDALONE_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 12 days ago, updated 6 days ago, no status
   - check above
- [#2718 Beta version of Viser visualizer](https://github.com/stack-of-tasks/pinocchio/pull/2718)
   - Created 7 days ago, updated 2 days ago, no status
   - Nice PR, interresting
   - Comments
       - Works with master branch of Viser, not the latest. 
       - Fix for Talos when same mesh for left/write
       - dependency cycle (includes Pinocchio), due to examples certainly.
       - Wilson th check the PR, then Joris/Guilhem to see how to progress on this

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#729 Update pixi lockfile](https://github.com/coal-library/coal/pull/729)
   - Created 6 days ago, merged 5 days ago
   - Montlhy dependency PR
- [#730 build(deps): bump cachix/cachix-action from 15 to 16](https://github.com/coal-library/coal/pull/730)
   - Created 5 days ago, merged 5 days ago
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - Created 139 days ago, merged 3 days ago
   - Merged of nanobind bindings

#### STACK-OF-TASKS/EIGENPY

- [#567 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/567)
   - Created 6 days ago, merged 5 days ago
   - Montlhy dependency PR
- [#569 build(deps): bump tarides/changelog-check-action from 2 to 3](https://github.com/stack-of-tasks/eigenpy/pull/569)
   - Created 5 days ago, merged 4 days ago
- [#568 build(deps): bump actions/cache from 3 to 4](https://github.com/stack-of-tasks/eigenpy/pull/568)
   - Created 5 days ago, merged 4 days ago
- [#570 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/570)
   - Created 3 days ago, merged 3 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2713 Add arm running in pixi workflow](https://github.com/stack-of-tasks/pinocchio/pull/2713)
   - Created 12 days ago, merged 6 days ago
   - New arm workflow, works fine except one problem related to per-label options (on arm, cppad codegen does not install, had to disable flag)
   - qemu - how to do an ARM Linux VM 
- [#2719 Add ROS 2 Kilted to CI jobs](https://github.com/stack-of-tasks/pinocchio/pull/2719)
   - Created 7 days ago, merged 6 days ago
   - New ROS distribution supported
- [#2715 Fix hasConfigurationLimit() for mimic joints to return empty vector](https://github.com/stack-of-tasks/pinocchio/pull/2715)
   - Created 12 days ago, merged 6 days ago
   - Problem with configuration joint limits (propagation of the parent to the child)
   - fixed
- [#2720 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2720)
   - Created 6 days ago, merged 4 days ago
   - Montlhy dependency PR
- [#2721 Update ROS section and CI badges in README](https://github.com/stack-of-tasks/pinocchio/pull/2721)
   - Created 4 days ago, merged 3 days ago
   - External contribution to add badge

#### SIMPLE-ROBOTICS/ALIGATOR

- [#332 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/332)
   - Created 6 days ago, merged 5 days ago
   - Montlhy dependency PR

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#89 Improvements to GUI reporting and interactivity for debug elements](https://github.com/Simple-Robotics/candlewick/pull/89)
   - Created 3 days ago, merged 3 days ago
   - Improves interactivity, quality of life


## 2025-06-30

### News

 - [name=Pierre-Guillaume] PUMA published for software development services around the Maestro robotics software stack https://puma.cnrs.fr/entreprise/consultation/512057?orgAcronyme=t5y
 - [name=Pierre-Guillaume] Discussions started between CNRS and Inria (transfer/valorisation services) about the consortium creation.

### Technical discussions

 - [name=Pierre-Guillaume] Recent open issues listed for all projects. Need a tag to filter the ones for the CoreDevs meeting otherwise too many listed.
     - issues with label "to_discuss"
     - new issues within the week
- [name=Justin] CppAD Problem https://github.com/stack-of-tasks/pinocchio/issues/2702
    - answered in the issue, will be in Pinocchio 4
- [name=Guilhem] Split python packaging https://github.com/jrl-umi3218/jrl-cmakemodules/pull/745
    - many PR in different repos related to separating C++ and Python packages, maybe multiple Python packages for different interpreters
    - Another approach by Joris, but a bit too intrusive
    - Some tests with Nix (conclusive), ongoing test with pypi 
    - issue with option name 
        - in example_robot_data : name is install_python_interface
        - in this PR : build_only_python_only vs build_only_python_interface
    - possible to build python interface while reusing the current C++ build
    - use "build_python_interface" and "build_standalone_python_interface"
        - using "bindings" instead of "interface" would be better, but too much impact
        - potentially change to "bindings" with jrl-cmakemodules v2
- [name=Joris] CI ARM Github
    - ARM CI put in place on Proxsuite (release) and Pinocchio, 
    - one test was failing, corrected
    - add this proc architecture on all the repos ?
        - yes


#### stack-of-tasks/pinocchio

 - Items to discuss:

   - [#2712 Release Pinocchio 3.5.0+ to ROS 2 Kilted?](https://github.com/stack-of-tasks/pinocchio/issues/2712)


#### simple-robotics/proxsuite

 - Items to discuss:

   - [#405 CMake regex failure due to special characters in path](https://github.com/Simple-Robotics/proxsuite/issues/405)
   - [#404 Using ProxSuite as a CMake subproject config failure](https://github.com/Simple-Robotics/proxsuite/issues/404)


#### simple-robotics/candlewick

 - Items to discuss:
   - [#4 Add standalone `Visualizer` runtime and IPC communication](https://github.com/Simple-Robotics/candlewick/issues/4)

### PR to review

#### COAL-LIBRARY/COAL


- [#728 merge #658 + #659](https://github.com/coal-library/coal/pull/728)
   - Created 18 hours ago, updated 12 hours ago, no status
   - PR so that both 658 and 659 can be merged independantly
   - Just for checking, will not be merged

#### STACK-OF-TASKS/PINOCCHIO


- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - Created 282 days ago, updated 80 days ago, status to review
- [#2713 Add arm running in pixi workflow](https://github.com/stack-of-tasks/pinocchio/pull/2713)
   - Created 3 days ago, updated 22 hours ago, status to review
   - completed, can be merged
- [#2714 CMake:  add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/stack-of-tasks/pinocchio/pull/2714)
   - Created 3 days ago, updated 20 hours ago, no status
   - see Technical Discussion
- [#2715 Fix hasConfigurationLimit() for mimic joints to return empty vector](https://github.com/stack-of-tasks/pinocchio/pull/2715)
   - Created 2 days ago, updated 1 days ago, no status
   - Forgotten function, brought back, but still to review since the same tangent function is used a bit further in the code
   - Make deadline explicit before Joris handle this
- [#2717 CMakeLists.txt: remove a duplicate option()](https://github.com/stack-of-tasks/pinocchio/pull/2717)
   - Created 7 minutes ago, updated 7 minutes ago, no status
   - Merged
   - How to automatically detect duplicates ?


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#726 CI: nix alls-green](https://github.com/coal-library/coal/pull/726)
   - Created 3 days ago, merged 3 days ago
- [#727 require octomap >= 1.8](https://github.com/coal-library/coal/pull/727)
   - Created 3 days ago, merged 2 days ago
- [#724 broadphase : add a functional API for collision and distance callbacks](https://github.com/coal-library/coal/pull/724)
   - Created 8 days ago, merged 3 days ago
   - Need to be exposed in the nanobind binding

#### STACK-OF-TASKS/EIGENPY

- [#559 ci: setup dependabot](https://github.com/stack-of-tasks/eigenpy/pull/559)
   - Created 3 days ago, merged 3 days ago
   - Activated, had trigerred many PRs, monthly basis
- [#558 CI: nix alls-green](https://github.com/stack-of-tasks/eigenpy/pull/558)
   - Created 3 days ago, merged 3 days ago
- [#566 ci: bump ROS](https://github.com/stack-of-tasks/eigenpy/pull/566)
   - Created 3 days ago, merged 3 days ago
   - Not trigered by dependabot, done manually, to check
- [#564 build(deps): bump cachix/cachix-action from 15 to 16](https://github.com/stack-of-tasks/eigenpy/pull/564)
   - Created 3 days ago, merged 3 days ago
- [#563 build(deps): bump actions/checkout from 3 to 4](https://github.com/stack-of-tasks/eigenpy/pull/563)
   - Created 3 days ago, merged 3 days ago
- [#562 build(deps): bump actions/create-github-app-token from 1 to 2](https://github.com/stack-of-tasks/eigenpy/pull/562)
   - Created 3 days ago, merged 3 days ago
- [#561 build(deps): bump prefix-dev/setup-pixi from 0.8.1 to 0.8.10](https://github.com/stack-of-tasks/eigenpy/pull/561)
   - Created 3 days ago, merged 3 days ago
- [#565 build(deps): bump cachix/install-nix-action from 27 to 31](https://github.com/stack-of-tasks/eigenpy/pull/565)
   - Created 3 days ago, merged 3 days ago

#### STACK-OF-TASKS/PINOCCHIO


- [#2706 Sync submodule cmake](https://github.com/stack-of-tasks/pinocchio/pull/2706)
   - Created 10 days ago, merged 3 days ago

#### SIMPLE-ROBOTICS/PROXSUITE


- [#403 aarch64 numerical precision issue in sparse_maros_meszaros](https://github.com/Simple-Robotics/proxsuite/pull/403)
   - Created 9 days ago, merged 17 hours ago
   - Numerical precision issue ? Stability issue ?
   - Potential deeper issue

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#12 CMake: sync submodule, bump min version to 3.22 & add pixi update workflow](https://github.com/Simple-Robotics/nanoeigenpy/pull/12)
   - Created 22 hours ago, merged 21 hours ago


## 2025-06-23

### News

 - [name=Hugo] SOFA community eager to collaborate more (further STC discussions)

### Technical discussions

- [name=Joris] Breaking API changes anticipated for Coal (v4)
    - Some classes were hardcoded scalar type -> changed for templated design
        - created issues bc people were doing forward declarations
        - also pb with SIMD operations for point vector eigen, memory alignment
        - creating an intermediate structure
        - hpp affordnce : class to find mesh locations for putting a feet, grasping
            - but no work anymore in this lib, so breaking change not a problem
        - Putting a guide online for migrating to the new API
    - Several object can use the same convex stored as shared pointer, which could be removed
    - Object BVH (Bounding Volume Hierarchy)
        - stores point cloud, can be set as convex shape
        - if so, create a convex and puth a shared pointer
        - hides that underneath is a convex (stores a shard pointer that points to itself)
        - put method as deprecated
        - add a new method to explicittely convert a bvh to convex (bvh object can be dropped after)
        - putting a constructor in convex (both for move and copy)
    - Check for additional breaking changes that would be desired (with a solid migration guide)
        - Study the broadphase (callback massively called)
    - google highway (https://github.com/google/highway)
        - use to create multiple optimzed libs depending on the cpu architecture
        - runtime dispatch (generate multiple .so and uses the most appropriate at runtime)
- [name=Justin] CppAD Problem https://github.com/stack-of-tasks/pinocchio/issues/2702
    - postponed for next week
- [name=Joris] How to handle forward declaration / typdefs [#716 convex: add missing typedefs for backward compatibility](https://github.com/coal-library/coal/pull/716)
    - linked to first point in Coal
    - add a fwd.h in Coal 
- [name=Wilson] Added aligator to [DeepWiki](https://deepwiki.com/Simple-Robotics/aligator) (wiki automatically generated by parsing the repo), perhaps interesting tool?
    - generates a readme automatically and proper wiki (with interresting things like graph of classes)
        - need to check how accurate
        - business model, availability long-term ?
- [name=Fabian] ProxSuite CMake issues: [404](https://github.com/Simple-Robotics/proxsuite/issues/404) and [405](https://github.com/Simple-Robotics/proxsuite/issues/405)
    - External contribution from Adobe dev
    - Joris to check and fix (minimal)
- [name=Guilhem] jrl-cmakemodules license [763](https://github.com/jrl-umi3218/jrl-cmakemodules/issues/763)
        - updated the list of licenses in headers, many GPL ! but used just for generating files
        - need to double check, clean
        - wait for v2 of jrl-cmakemodules
        - remove submodules in tarball
- [name=Wilson] Nanobind : PR will be merged this week
    - documentation to be done later (current solution is not satisfying and will have to be changed anyway)


### PR to review

#### COAL-LIBRARY/COAL

- [#724 broadphase : add a functional API for collision and distance callbacks](https://github.com/coal-library/coal/pull/724)
   - created 5 days ago, updated 4 days ago
   - can be merged
   - create an example afterward (python lambda)

#### STACK-OF-TASKS/EIGENPY

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 279 days ago, updated 77 days ago
- [#2706 Sync submodule cmake](https://github.com/stack-of-tasks/pinocchio/pull/2706)
   - created 6 days ago, updated 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR


#### SIMPLE-ROBOTICS/PROXSUITE

- [#403 Nix](https://github.com/Simple-Robotics/proxsuite/pull/403)
   - created 6 days ago, updated 6 days ago
   - Problem appears only on Linux ARM (thanks to Nix)

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#715 flake.lock: Update](https://github.com/coal-library/coal/pull/715)
   - created 11 days ago
- [#717 Try to use more recent ros-industrial version](https://github.com/coal-library/coal/pull/717)
   - created 7 days ago
- [#718 Configure dependabot](https://github.com/coal-library/coal/pull/718)
   - created 6 days ago
- [#722 build(deps): bump prefix-dev/setup-pixi from 0.8.1 to 0.8.10](https://github.com/coal-library/coal/pull/722)
   - created 6 days ago
- [#723 build(deps): bump tarides/changelog-check-action from 2 to 3](https://github.com/coal-library/coal/pull/723)
   - created 6 days ago
- [#721 build(deps): bump actions/setup-python from 4 to 5](https://github.com/coal-library/coal/pull/721)
   - created 6 days ago
- [#719 build(deps): bump cachix/install-nix-action from 27 to 31](https://github.com/coal-library/coal/pull/719)
   - created 6 days ago
- [#720 build(deps): bump actions/create-github-app-token from 1 to 2](https://github.com/coal-library/coal/pull/720)
   - created 6 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2704 build(deps): bump prefix-dev/setup-pixi from 0.8.8 to 0.8.10](https://github.com/stack-of-tasks/pinocchio/pull/2704)
   - created 7 days ago
- [#2705 Fix issue #2703](https://github.com/stack-of-tasks/pinocchio/pull/2705)
   - created 7 days ago
- [#2707 Fix : make nvSubtree consistent with mimic joint in all configuration](https://github.com/stack-of-tasks/pinocchio/pull/2707)
   - created 6 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#86 Fix shadow pass using camera frustum, remove using-decl for `coal::OBB`](https://github.com/Simple-Robotics/candlewick/pull/86)
   - created 5 days ago


## 2025-06-16

### News

 - [name=Pierre-Guillaume] 
     - Presentation of the Maestro initiative during a  during a panel discussion at VivaTech
     - New software engineer recruted to oversee the development of the Simple simulator (should arrive in october)

### Technical discussions

 - [name=Joris]
    - Breaking API change of Coal antiipated for Coal (v4) - to discuss next week
    - Still waiting for Eigen PR to be merged by Google
        -  https://gitlab.com/libeigen/eigen/-/merge_requests/1897
 - [name=Joris] Add issues to discuss in the agenda of the meeting (need to support tags, update the scripts).

### Issues to discuss

 - [name=Justin] CppAD Problem https://github.com/stack-of-tasks/pinocchio/issues/2702

### PR to review

#### COAL-LIBRARY/COAL

- [#715 flake.lock: Update](https://github.com/coal-library/coal/pull/715)
   - created 4 days ago, updated 4 days ago
   - Change for required flag in the PR like in Pinocchio so that no marge if CI fails (should be default behavior).
   - Here CI fails for ROS. Can indeed merge is CI ok for Nix.

#### STACK-OF-TASKS/EIGENPY


#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 272 days ago, updated 70 days ago
- [#2704 build(deps): bump prefix-dev/setup-pixi from 0.8.8 to 0.8.10](https://github.com/stack-of-tasks/pinocchio/pull/2704)
   - created 0 days ago, updated 0 days ago
   - Already merged

#### SIMPLE-ROBOTICS/ALIGATOR

- [#331 Add a Python test for MPC-like iteration](https://github.com/Simple-Robotics/aligator/pull/331)
   - created 3 days ago, updated 3 days ago
   - Random NaN after some iterations. Initialisation issue. Need to check with valgrind
 

#### SIMPLE-ROBOTICS/PROXSUITE

#### SIMPLE-ROBOTICS/SIMPLE

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#716 convex: add missing typedefs for backward compatibility](https://github.com/coal-library/coal/pull/716)
   - created 4 days ago
   - Putting in place typedef (e.g., Triangle) - problem with projects that do forward declaration of these types.
       - one solution. Header of forward declarations with typedefs
       - to discuss next week

#### STACK-OF-TASKS/PINOCCHIO

- [#2699 build(deps): bump ros-industrial/industrial_ci from 7083afac1ddf852a2923757a7ef588adaba841a9 to e3d16c224caf4832cf68e74093eb70f3a979b4cc](https://github.com/stack-of-tasks/pinocchio/pull/2699)
   - created 7 days ag

#### SIMPLE-ROBOTICS/PROXSUITE

- [#402 update readme](https://github.com/Simple-Robotics/proxsuite/pull/402)
   - created 10 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#79 next](https://github.com/Simple-Robotics/candlewick/pull/79)
   - created 6 days ago
   - many internal changes
- [#81 Fix building with the next version of Coal (devel)](https://github.com/Simple-Robotics/candlewick/pull/81)
   - created 4 days ago
   - solves various issues to use with Coal (devel)
- [#83 Fix FFmpeg not being actually optional when building, add warnings when calling `Visualizer` recording settings in this case](https://github.com/Simple-Robotics/candlewick/pull/83)
   - created 4 days ago
- [#84 Fix display issues with capsules, missing colour for primitives](https://github.com/Simple-Robotics/candlewick/pull/84)
   - created 4 days ago

## 2025-06-02

### News

- [name=Pierre-Guillaume Raverdy] Code for Simple is online
    - Not yet a release
    - Requires upcoming Pinocchio4 (on Simple repo - some compilation issues, monitoring)
    - When to discuss as part of Maestro ? Wait for first release or no ?
        - Start now, will help the first release (recurring topic in the technical discussion)

### Technical discussions

- [name=Joris Vaillant] Breaking changes in Coal (devel branch).
    - ConvexBase are templated now
    - Need to minimize breaking changes in upcomming release (check with Louis)
- [name=Pierre-Guillaume Raverdy] What about recuring PR (Pixi, Ros ) in the agenda ?
    - Only keep in the agenda if the CI fails, can be an important topic
- [name=Guilhem Saurel] Script to generate different cron start date for different projects (avoid starting everything at the same time) https://github.com/nim65s/scripts/blob/hm/md5cron.py (monthly only for now)


### PR to review

#### COAL-LIBRARY/COAL

- [#709 CMake: add COAL_DISABLE_HPP_FCL_WARNINGS option](https://github.com/coal-library/coal/pull/709)
   - created 7 days ago, updated 6 days ago
   - ready for review
- [#711 Update pixi lockfile](https://github.com/coal-library/coal/pull/711)
   - created 1 days ago, updated 1 days ago
   - CI fails, just ROS, minimal

#### STACK-OF-TASKS/EIGENPY

- [#554 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/554)
   - created 1 days ago, updated 1 days ago
   - need to check CI (JRL), just a rebase ?

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 258 days ago, updated 56 days ago
- [#2686 CMake: add COAL_DISABLE_HPP_FCL_WARNINGS](https://github.com/stack-of-tasks/pinocchio/pull/2686)
   - created 7 days ago, updated 6 days ago
   - to review, ongoing discussions
- [#2692 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2692)
   - created 1 days ago, updated 1 days ago
   - CI fails (APT) need to check
- [#2693 build(deps): bump ros-industrial/industrial_ci from 16472786c1ffc53596007da4318db98d1f677933 to 7083afac1ddf852a2923757a7ef588adaba841a9](https://github.com/stack-of-tasks/pinocchio/pull/2693)
   - created 0 days ago, updated 0 days ago
   - network issue during the CI, just need to restart it

#### SIMPLE-ROBOTICS/ALIGATOR

- [#327 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/327)
   - created 1 days ago, updated 1 days ago
   - CI fails, need to add tag for changelog

#### SIMPLE-ROBOTICS/PROXSUITE


#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#131 Update pixi lockfile](https://github.com/Simple-Robotics/proxsuite-nlp/pull/131)
   - created 1 days ago, updated 1 days ago
   - closed
   - archiving the repo now (remove from meeting agenda)

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the week

#### STACK-OF-TASKS/EIGENPY

- [#553 readme: update apt key usage, fix #552](https://github.com/stack-of-tasks/eigenpy/pull/553)
   - created 13 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2684 Add further check of input arguments for kinematics Jacobians](https://github.com/stack-of-tasks/pinocchio/pull/2684)
   - created 9 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#322 solvers : make proxddp algo's `Results` class copyable again (in C++ and Python)](https://github.com/Simple-Robotics/aligator/pull/322)
   - created 6 days ago
- [#324 solvers : use move workspace and results assignment operators in `SolverProxDDP::setup()`](https://github.com/Simple-Robotics/aligator/pull/324)
   - created 6 days ago
- [#325 Update minimum eigenpy in readme and cmake](https://github.com/Simple-Robotics/aligator/pull/325)
   - created 6 days ago
- [#326 Added wheeled inverted pendulum dynamics](https://github.com/Simple-Robotics/aligator/pull/326)
   - created 6 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#71 Better shadows: soft shadows using percentage-closer filtering (PCF), tighter shadow frustum (from scene AABBs)](https://github.com/Simple-Robotics/candlewick/pull/71)
   - created 7 days ago
- [#74 Fix hangs when `Renderer` or `Visualizer` are destroyed](https://github.com/Simple-Robotics/candlewick/pull/74)
   - created 3 days ago
- [#75 pixi: update lockfile](https://github.com/Simple-Robotics/candlewick/pull/75)
   - created 2 days ago

## 2025-05-26

### News

 - [name=Joris Vaillant] Release pinocchio 3.7
     - Stable version which will be merged in Pinocchio 4
     - Some minor remaining PR to come for Pinocchio 3
     - [Panda3d](https://www.panda3d.org/) for offscreen rendering
 - [name=Pierre-Guillaume Raverdy] Code for Simple is almost online
     - Not yet a release

### Technical discussions

 - [name=Joris Vaillant] License JRL-CMakeModules
     - ROS comment that license is not clear
     - Different licenses used in the module, need to conform with ROS package process/licensing
         - mostly GPLv3, but package not distributed, helps to generate code
         - some distributed files (file external) are in GPL
     - need to sort for v2 version of jrl-cmakemodules
 - [name=Joris Vaillant] Pinocchio 4 CI Debug on Simple-Robotics/pinocchio
     - Created to sort/complete the Github CI, avoid exposing the branch to the general public
     - helps to experiment without too much visibility
     - CTA: Change the description in Github
 - [name=Guilhem Saurel] warning hpp-fcl: flag to opt-out
    - add a flag for pinocchio v3
    - for pinocchio v4, change hpp-fcl to coal
    - prepare a new release for COAL (v4)
        - new PRs from Louis and Nanobind (breaking changes)

### PR to review

#### COAL-LIBRARY/COAL


#### STACK-OF-TASKS/EIGENPY

- [#553 readme: update apt key usage, fix #552](https://github.com/stack-of-tasks/eigenpy/pull/553)
   - created 3 days ago, updated 1 days ago
   - can be merged directly (no source file impacted)

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 248 days ago, updated 46 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#399 topic/osqp: Add the OSQP solver in ProxSuite](https://github.com/Simple-Robotics/proxsuite/pull/399)
   - created 4 days ago, updated 3 days ago
   - Set to WIP

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the past 2 weeks

#### COAL-LIBRARY/COAL

- [#661 subscribe to ROS buildfarm mails](https://github.com/coal-library/coal/pull/661)
   - created 4 days ago
- [#704 CMake: qhull system or nothing](https://github.com/coal-library/coal/pull/704)
   - created 10 days ago
- [#705 ci: fix nix](https://github.com/coal-library/coal/pull/705)
   - created 10 days ago


#### STACK-OF-TASKS/EIGENPY

- [#534 subscribe to ROS buildfarm mails](https://github.com/stack-of-tasks/eigenpy/pull/534)
   - created 4 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2589 subscribe to ROS buildfarm mails](https://github.com/stack-of-tasks/pinocchio/pull/2589)
   - created 4 days ago
- [#2593 build(deps): bump prefix-dev/setup-pixi from 0.8.2 to 0.8.3](https://github.com/stack-of-tasks/pinocchio/pull/2593)
   - created 0 days ago
- [#2684 Add further check of input arguments for kinematics Jacobians](https://github.com/stack-of-tasks/pinocchio/pull/2684)
   - created 2 days ago, updated 2 days ago
- [#2680 Remove support of 20.04 in linux CI](https://github.com/stack-of-tasks/pinocchio/pull/2680)
   - created 6 days ago
   - To discuss with potential industrial members
   - Python 3.9 still supported. 
       - APT: min 3.10
       - Python foundation supports from 3.9 to 3.13 (5 versions)

#### SIMPLE-ROBOTICS/ALIGATOR

- [#317 Exposing vs in ProxDDP result](https://github.com/Simple-Robotics/aligator/pull/317)
   - created 11 days ago
- [#320 CMakeLists.txt : Update minimum required version of CMake to 3.22](https://github.com/Simple-Robotics/aligator/pull/320)
   - created 3 days ago

#### SIMPLE-ROBOTICS/PROXSUITE


#### SIMPLE-ROBOTICS/CANDLEWICK

- [#58 RobotScene : Add order-independent transparency](https://github.com/Simple-Robotics/candlewick/pull/58)
   - created 7 days ago
- [#59 Implement and use type-safe command buffer uniform push wrappers](https://github.com/Simple-Robotics/candlewick/pull/59)
   - created 6 days ago
- [#60 [core] Revamp SSAO, depth and shadow map pass classes - add move constructors, assignment op, and destructors](https://github.com/Simple-Robotics/candlewick/pull/60)
   - created 6 days ago
- [#61 Rework texture downloader, screenshot capture and video recording, fix `CommandBuffer::submitAndAcquireFence()` not setting the internal pointer to null, fix velocity arrow direction in `RobotDebugScene`](https://github.com/Simple-Robotics/candlewick/pull/61)
   - created 7 days ago
- [#62 Video and screenshot recording: follow-up](https://github.com/Simple-Robotics/candlewick/pull/62)
   - created 6 days ago
- [#63 Video and screenshot recording : part 3](https://github.com/Simple-Robotics/candlewick/pull/63)
   - created 5 days ago
- [#64 [utils | third-party] switch from `stb_image_write.h` to `fpng` for writing PNG files](https://github.com/Simple-Robotics/candlewick/pull/64)
   - created 5 days ago
- [#65 multibody/Visualizer : add `startRecording()`, `stopRecording()` functions, expose to Python](https://github.com/Simple-Robotics/candlewick/pull/65)
   - created 5 days ago
- [#69 Add support for multiple directional lights - with shadow mapping !](https://github.com/Simple-Robotics/candlewick/pull/69)
   - created 3 days ago
- [#70 multibody/Visualizer : use `H` key to toggle GUI](https://github.com/Simple-Robotics/candlewick/pull/70)
   - created 1 days ago


## 2025-05-12

### News

 - [name=Fabian Schramm] Removed CLA (Contributor License Agreement) for proxsuite
 - [name=Joris] New release of Aligator (v0.14) with no dependency on proxsuite-nlp

### Technical discussions

 - [name=Pierre-Guillaume] Preparation of technical roadmaps for some of the software this week.

### PR to review

#### COAL-LIBRARY/COAL

#### STACK-OF-TASKS/EIGENPY

#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 234 days ago, updated 32 days ago, **pr status to review**

#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 51 days ago, updated 4 days ago, **pr status to review**
   - to be closed, improved implementaton on another branch

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#701 Update pixi lockfile](https://github.com/coal-library/coal/pull/701)
   - created 8 days ago

#### STACK-OF-TASKS/EIGENPY

- [#551 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/551)
   - created 6 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2672 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2672)
   - created 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#310 Move constraint sets from `proxsuite-nlp`](https://github.com/Simple-Robotics/aligator/pull/310)
   - created 3 days ago
- [#312 Add polymorphic value wrapper, remove dependence on `proxsuite-nlp` headers](https://github.com/Simple-Robotics/aligator/pull/312)
   - created 3 days ago
- [#309 Merge parts of `proxsuite-nlp` (manifolds and constraints) into aligator](https://github.com/Simple-Robotics/aligator/pull/309)
   - created 4 days ago
- [#313 Managed matrix](https://github.com/Simple-Robotics/aligator/pull/313)
   - created 2 days ago
   - allows to have Eigen matrix 
- [#314 topic/next : aligator 0.14](https://github.com/Simple-Robotics/aligator/pull/314)
   - created 2 days ago
 
## 2025-05-05

### News

 - [name=Pierre-Guillaume] Inria's workshop on software for robotics moved to September (to avoid conflict with 2rm workshop)

### Technical discussions

 - [name=Pierre-Guillaume] As a reminder, the agenda has no more "wip" PRs
 - [name=Pierre-Guillaume] Discuss on preparing roadmaps for the different software (identifying new features planned, defining a release process)
     - should we have a roadmap written somewhere, so that users know what will happen, updated twice a year ?
         - Do this for 3 projects first (pinocchio, coal, aligator) to see if it works
         - research projects may be difficult? 
             - nobody full-time 
             - research opportunities change priorities and hard to predict the outcome
         - We try and see
     - Can we have monthly release ?
         - Is it desirable? 
         - what about hard deadline ? 
             - try more like a prediction/objective but no guarantees (especially manpower)
         - timing of pinocchio3
             - took a long time, was announced way before but postponned
     - How is SOFA doing?
         - example of [bi-annual roadmap](https://www.sofa-framework.org/consortium/roadmap/)
         - feedback: content/how to do has changed overtime since it was done periodically 
         - overall, it eases the technical governance
 - [name=Joris] Remove CLA in proxsuite ?
     - Why a CLA (Contributor License Agreements) needed in ProxSuite
     - Confirm to whom the rights are assigned (unclear). Valid CLA? 
     - it seems we have added it because osqp had a similar cla: https://gist.github.com/jcarpent/67dfb0cbcc4a1a4ed0d8dea190af9d08 (written on top "adapted from osqp")

### PR to review

#### COAL-LIBRARY/COAL

- [#702 [cmake] Remove superfluous call to `FINDPYTHON`](https://github.com/coal-library/coal/pull/702)
   - created 3 days ago, updated 3 days ago
   - ref. https://github.com/coal-library/coal/commit/041ac9f3ad90a0fe564774233e665831e9ce8a84
   - better to avoid transitive dependency ?
   - ref. https://cmake.org/cmake/help/latest/module/FindPythonInterp.html :`PYTHON_EXECUTABLE`
   - CAPS for variables
   - Related to: https://github.com/jrl-umi3218/jrl-cmakemodules/pull/761

#### STACK-OF-TASKS/EIGENPY


#### STACK-OF-TASKS/PINOCCHIO

- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 227 days ago, updated 25 days ago
- [#2672 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2672)
   - created 0 days ago, updated 0 days ago
   - merged

#### SIMPLE-ROBOTICS/ALIGATOR


#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 47 days ago, updated 34 days ago
- [#397 Allow users-defined `THROW_PRETTY` and `CHECK_ARGUMENT_SIZE` macros](https://github.com/Simple-Robotics/proxsuite/pull/397)
   - created 5 days ago, updated 5 days ago
   - to close since author does not respond, may be reopened later (may be related to CLA taking a lot of time to validate)

#### SIMPLE-ROBOTICS/CANDLEWICK


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#699 Fix autodoc inner class](https://github.com/coal-library/coal/pull/699)
   - created 7 days ago
   - issue with generating the inner class prototype from the xml.
   - Alternative: 
       - https://robotpy.github.io/cxxheaderparser/
       - https://pypi.org/project/doxmlparser/ (in-tree doxygen)
- [#700 Dont update master](https://github.com/coal-library/coal/pull/700)
   - created 6 days ago
- [#701 Update pixi lockfile](https://github.com/coal-library/coal/pull/701)
   - created 4 days ago

#### STACK-OF-TASKS/EIGENPY

- [#547 Use devel as default branch](https://github.com/stack-of-tasks/eigenpy/pull/547)
   - created 6 days ago
- [#549 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/549)
   - created 4 days ago
- [#551 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/551)
   - created 2 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2665 build(deps): bump ros-industrial/industrial_ci from cfe5c929f7dbb0374c01bc26821ec8eb72f6d4e8 to 16472786c1ffc53596007da4318db98d1f677933](https://github.com/stack-of-tasks/pinocchio/pull/2665)
   - created 7 days ago
- [#2666 Change default branch](https://github.com/stack-of-tasks/pinocchio/pull/2666)
   - created 6 days ago
- [#2668 Implement `captureImage` for Panda3D visualizer](https://github.com/stack-of-tasks/pinocchio/pull/2668)
   - created 5 days ago
- [#2671 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2671)
   - created 4 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#297 Change work in progress branch](https://github.com/Simple-Robotics/aligator/pull/297)
   - created 6 days ago
- [#298 Add CMake macro `aligator_create_python_extension()` to export](https://github.com/Simple-Robotics/aligator/pull/298)
   - created 6 days ago
- [#299 Merge expose-stage-data.cpp into expose-stage.cpp](https://github.com/Simple-Robotics/aligator/pull/299)
   - created 5 days ago
- [#300 [gar] Add `LqrProblemTpl::isApprox()` and helper `lqrKnotsSameDim`, check dimensions in `LqrKnotTpl::isApprox()`](https://github.com/Simple-Robotics/aligator/pull/300)
   - created 5 days ago
- [#301 [gar] Add fwd header, rename `{ riccati-impl.hpp => riccati-kernel.hpp }`](https://github.com/Simple-Robotics/aligator/pull/301)
   - created 5 days ago
- [#304 [python] make BlkMatrixPythonVisitor an incomplete type when template argument is wrong](https://github.com/Simple-Robotics/aligator/pull/304)
   - created 5 days ago
- [#305 .gersemirc : add bench dir](https://github.com/Simple-Robotics/aligator/pull/305)
   - created 5 days ago
- [#306 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/306)
   - created 4 days ago
- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 185 days ago
- [#307 Officially remove support for Pinocchio 2, require Pinocchio >= 3.4](https://github.com/Simple-Robotics/aligator/pull/307)
   - created 3 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#395 Use devel as default branch](https://github.com/Simple-Robotics/proxsuite/pull/395)
   - created 6 days ago

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#130 Update pixi lockfile](https://github.com/Simple-Robotics/proxsuite-nlp/pull/130)
   - created 4 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#10 Add equivalent to eigenpy::register_symbolic_link_to_registered_type](https://github.com/Simple-Robotics/nanoeigenpy/pull/10)
   - created 20 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#39 determine Python API's default shader path at runtime using relative path](https://github.com/Simple-Robotics/candlewick/pull/39)
   - created 8 days ago
- [#40 Remove std::optional for `Visualizer::debugScene`, initialize in ctor](https://github.com/Simple-Robotics/candlewick/pull/40)
   - created 7 days ago
- [#41 Remove print statement in `__init__.py`](https://github.com/Simple-Robotics/candlewick/pull/41)
   - created 7 days ago
- [#42 Add pixi lockfile update workflow](https://github.com/Simple-Robotics/candlewick/pull/42)
   - created 7 days ago
- [#43 [python] Fix `Visualizer` getters for Pinocchio 3.5.0](https://github.com/Simple-Robotics/candlewick/pull/43)
   - created 7 days ago
- [#44 Fix shader paths again](https://github.com/Simple-Robotics/candlewick/pull/44)
   - created 6 days ago

## 2025-04-28

### News

 - [name=Joris Vaillant] Inria TechDays on Robotics on June 18th/19th ? Conflict with CNRS 2rm TechDays. Ask to postpone

### Technical discussions

 - [name=Joris Vaillant] Ubuntu 20.04 no more available in Github Actions
 - [name=Pierre-Guillaume] CoreDevs meeting organisation. Stop showing WIP PRs from now on


### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 445 days ago, updated 46 days ago, **pr status wip**
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 71 days ago, updated 49 days ago, **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 67 days ago, updated 6 days ago, **pr status wip**
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 65 days ago, updated 30 days ago, **pr status wip**

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 708 days ago, updated 49 days ago, **pr status wip**

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 228 days ago, updated 39 days ago, **pr status wip**
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 220 days ago, updated 18 days ago, **pr status to review**
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 106 days ago, updated 49 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 73 days ago, updated 49 days ago, **pr status wip**
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 72 days ago, updated 49 days ago, **pr status wip**
- [#2652 Update mjcf parser](https://github.com/stack-of-tasks/pinocchio/pull/2652)
   - created 9 days ago, updated 9 days ago
   - this will soon get merged in devel, this PR should be closed once explanations are given to the contributor
   - To be closed
- [#2654 [WIP] Introduce the next-generation of Python bindings using nanobind](https://github.com/stack-of-tasks/pinocchio/pull/2654)
   - created 8 days ago, updated 6 days ago
   - Will be closed soon (rather introduced on topic-simulation)
- [#2664 Introducing model graph](https://github.com/stack-of-tasks/pinocchio/pull/2664)
   - created 3 days ago, updated 3 days ago
   - define the model as intermediate graph structures
   - back to wip
- [#2665 build(deps): bump ros-industrial/industrial_ci from cfe5c929f7dbb0374c01bc26821ec8eb72f6d4e8 to 16472786c1ffc53596007da4318db98d1f677933](https://github.com/stack-of-tasks/pinocchio/pull/2665)
   - created 0 days ago, updated 0 days ago
   - merged

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 175 days ago, updated 1 days ago, **pr status wip**

#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 37 days ago, updated 24 days ago, **pr status to review**
   - Lucas will discuss with Justin
- [#393 Allow users to provide their own THROW_PRETTY and CHECK_ARGUMENT_SIZE macros](https://github.com/Simple-Robotics/proxsuite/pull/393)
   - created 5 days ago, updated 3 days ago
   - Ping the contributor (use max instead of infinity)

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#10 Add equivalent to eigenpy::register_symbolic_link_to_registered_type](https://github.com/Simple-Robotics/nanoeigenpy/pull/10)
   - created 10 days ago, updated 10 days ago
   - reviews taken into account
   - introduce a deprecation with a date
   - possibly introduce the deprecated C++17 tag 

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#37 Add Candlewick runtime (executable)](https://github.com/Simple-Robotics/candlewick/pull/37)
   - created 15 days ago, updated 11 days ago, **pr status wip**
- [#39 determine Python API's default shader path at runtime using relative path](https://github.com/Simple-Robotics/candlewick/pull/39)
   - created 1 days ago, updated 1 days ago
   - merged

### PR merged within the past 2 weeks



#### COAL-LIBRARY/COAL

- [#693 flake.lock: Update](https://github.com/coal-library/coal/pull/693)
   - created 6 days ago
- [#682 Add support for Convex16 and Convex32](https://github.com/coal-library/coal/pull/682)
   - created 18 days ago
- [#697 Fix autodoc generation on Windows](https://github.com/coal-library/coal/pull/697)
   - created 3 days ago


#### STACK-OF-TASKS/EIGENPY

- [#546 Update C++ standard for clang-format to 11, apply updated formatting rules](https://github.com/stack-of-tasks/eigenpy/pull/546)
   - created 3 days ago
- [#545 Add user-defined literal `""_a` for `bp::arg`](https://github.com/stack-of-tasks/eigenpy/pull/545)
   - created 3 days ago


#### STACK-OF-TASKS/PINOCCHIO

- [#2646 build(deps): bump prefix-dev/setup-pixi from 0.8.4 to 0.8.5](https://github.com/stack-of-tasks/pinocchio/pull/2646)
   - created 4 days ago
- [#2648 unittest/python : add visualizer bindings visitor test, add CMake util to create C++ Python modules for tests](https://github.com/stack-of-tasks/pinocchio/pull/2648)
   - created 2 days ago
- [#2647 [python] Fix for getters in VisualizerPythonVisitor](https://github.com/stack-of-tasks/pinocchio/pull/2647)
   - created 3 days ago
- [#2658 build(deps): bump prefix-dev/setup-pixi from 0.8.5 to 0.8.8](https://github.com/stack-of-tasks/pinocchio/pull/2658)
   - created 7 days ago
- [#2657 build(deps): bump ros-industrial/industrial_ci from 3e67ec54d63496e076267392148a26229740befc to cfe5c929f7dbb0374c01bc26821ec8eb72f6d4e8](https://github.com/stack-of-tasks/pinocchio/pull/2657)
   - created 7 days ago
- [#2659 Fix custom scalar support](https://github.com/stack-of-tasks/pinocchio/pull/2659)
   - created 6 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#286 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/aligator/pull/286)
   - created 11 days ago
- [#291 Update CITATIONS.bib and CITATION.cff](https://github.com/Simple-Robotics/aligator/pull/291)
   - created 4 days ago
- [#292 Reverse sign of StateErrorResidual](https://github.com/Simple-Robotics/aligator/pull/292)
   - created 2 days ago
- [#293 macos-linux-pixi workflow: change branch rules](https://github.com/Simple-Robotics/aligator/pull/293)
   - created 2 days ago
- [#294 Fix segfault in `FrameCollisionResidual`, add corresponding test in `test_frames.py`](https://github.com/Simple-Robotics/aligator/pull/294)
   - created 2 days ago

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#129 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/proxsuite-nlp/pull/129)
   - created 11 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#38 Add second constructor to `RobotScene`, streamline `Visualizer`](https://github.com/Simple-Robotics/candlewick/pull/38)
   - created 7 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#11 Fix Windows installation issue](https://github.com/Simple-Robotics/nanoeigenpy/pull/11)
   - created 3 days ago


## 2025-04-14

### News

- [name=Pierre-Guillaume] In the context of TIRREX, completing a PUMA proposal for software development tasks (jrl-cmakemodules v2, integrating with gazebo/blender/..., POC for ProxSuite, POC for RTSan checks, QPBenchmarks)

### Technical discussions

- [name=Joris] disussion wrt managing PR for fork of fork (check Github documentation)

- [name=Wilson] nanoeigenpy as a host dependency of Coal. We use headers from nanoeigenpy. When we will use Pixi build, need to handle more properly host, build and runtime dependencies. 
  - Candlewick will have a new runtime (executable target `candlewick_visualizer`, WIP name). Exists because async renderer without IPC isn't possible with just threads (at least not on macOS which requires `SDL_Window` be launched/interacted with on main thread)

### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 434 days ago, updated 35 days ago, **pr status wip**
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 60 days ago, updated 38 days ago, **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 56 days ago, updated 6 days ago, **pr status wip**
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 54 days ago, updated 19 days ago, **pr status wip**
- [#682 Add support for Convex16 and Convex32](https://github.com/coal-library/coal/pull/682)
   - created 14 days ago, updated 5 days ago, **pr status wip**

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 697 days ago, updated 38 days ago, **pr status wip**

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 217 days ago, updated 28 days ago, **pr status wip**
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 209 days ago, updated 7 days ago, **pr status to review**
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 95 days ago, updated 38 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 62 days ago, updated 38 days ago, **pr status wip**
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 61 days ago, updated 38 days ago, **pr status wip**
- [#2646 build(deps): bump prefix-dev/setup-pixi from 0.8.4 to 0.8.5](https://github.com/stack-of-tasks/pinocchio/pull/2646)
   - created 0 days ago, updated 0 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 164 days ago, updated 11 days ago, **pr status wip**
- [#286 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/aligator/pull/286)
   - created 7 days ago, updated 7 days ago
   - check with valgrind wrt Ubuntu/Python 3.9

#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 26 days ago, updated 13 days ago, **pr status to review**

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#129 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/proxsuite-nlp/pull/129)
   - created 7 days ago, updated 7 days ago
   - check for putting automatically labels on PRv(wrt changelog)?

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#37 Add Candlewick runtime (executable)](https://github.com/Simple-Robotics/candlewick/pull/37)
   - created 4 days ago, updated 3 days ago

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#688 Remove useless #ifdef COAL_WITH_CXX11_SUPPORT](https://github.com/coal-library/coal/pull/688)
   - created 8 days ago
- [#690 [pre-commit.ci] pre-commit autoupdate](https://github.com/coal-library/coal/pull/690)
   - created 7 days ago
- [#689 Sync submodule CMake](https://github.com/coal-library/coal/pull/689)
   - created 7 days ago
- [#693 flake.lock: Update](https://github.com/coal-library/coal/pull/693)
   - created 2 days ago

#### STACK-OF-TASKS/EIGENPY

- [#542 Fix issue on Eigen 3.4.90 + sync submodule CMake](https://github.com/stack-of-tasks/eigenpy/pull/542)
   - created 10 days ago
- [#543 [pre-commit.ci] pre-commit autoupdate](https://github.com/stack-of-tasks/eigenpy/pull/543)
   - created 7 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2640 build(deps): bump actions/create-github-app-token from 1 to 2](https://github.com/stack-of-tasks/pinocchio/pull/2640)
   - created 7 days ago
- [#2644 [Model] Improve error message](https://github.com/stack-of-tasks/pinocchio/pull/2644)
   - created 6 days ago

#### SIMPLE-ROBOTICS/PROXSUITE

- [#391 [pre-commit.ci] pre-commit autoupdate](https://github.com/Simple-Robotics/proxsuite/pull/391)
   - created 7 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#31 Fix Coal primitive loader for `GEOM_BOX`](https://github.com/Simple-Robotics/candlewick/pull/31)
   - created 10 days ago
   - fix issue wrt length box de Coal  (size was 2x)
- [#34 Move python bindings dir](https://github.com/Simple-Robotics/candlewick/pull/34)
   - created 6 days ago
- [#35 Change main render passes' transparency blend state](https://github.com/Simple-Robotics/candlewick/pull/35)
   - created 5 days ago
   - pb with transparency of body of Upkie
- [#36 GUI updates: fix HUD toggles, add "about" window, add robot info table, add `GeometryObject` and plane toggles](https://github.com/Simple-Robotics/candlewick/pull/36)
   - created 5 days ago
   - Added UI panel to manipulate meshes in realtime
   - How to save/reuse the changes? Not handled for now
- [#38 Add second constructor to `RobotScene`, streamline `Visualizer`](https://github.com/Simple-Robotics/candlewick/pull/38)
   - created 3 days ago

## 2025-04-07

### News

 - [name=Pierre-Guillaume] Adding CANDLEWICK as a project tracked by Maestro. 

### Technical discussions

 - [name=Wilson] Waiting for nanoeigenpy and candlewick to be added to condaforge
     - https://github.com/conda-forge/staged-recipes/pull/29606 (nanoeigenpy)
     - https://github.com/conda-forge/staged-recipes/pull/29627 (candlewick)

### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 427 days ago, updated 28 days ago, **pr status wip**
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 53 days ago, updated 31 days ago, **pr status wip**
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 49 days ago, updated 7 days ago, **pr status wip**
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 47 days ago, updated 12 days ago, **pr status wip**
- [#682 Add support for Convex16 and Convex32](https://github.com/coal-library/coal/pull/682)
   - created 7 days ago, updated 4 days ago **pr status wip**
   - reduce memory footprint of meshes in Coal 
   - Windows documentation is failing (related to parser)
- [#688 Remove useless #ifdef COAL_WITH_CXX11_SUPPORT](https://github.com/coal-library/coal/pull/688)
   - created 1 days ago, updated 1 days ago
   - merged

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 690 days ago, updated 31 days ago, **pr status wip**
- [#542 Fix issue on Eigen 3.4.90 + sync submodule CMake](https://github.com/stack-of-tasks/eigenpy/pull/542)
   - created 3 days ago, updated 2 days ago, **pr status wip**


#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 210 days ago, updated 21 days ago, **pr status wip**
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 202 days ago, updated 31 days ago, **pr status to review**
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 88 days ago, updated 31 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 55 days ago, updated 31 days ago, **pr status wip**
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 54 days ago, updated 31 days ago, **pr status wip**
- [#2617 Fix hpp-fcl dependency](https://github.com/stack-of-tasks/pinocchio/pull/2617)
   - created 24 days ago, updated 14 days ago, **pr status wip**
- [#2640 build(deps): bump actions/create-github-app-token from 1 to 2](https://github.com/stack-of-tasks/pinocchio/pull/2640)
   - created 0 days ago, updated 0 days ago
   - merged

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 157 days ago, updated 4 days ago, **pr status wip**
   - still ongoing work

#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 19 days ago, updated 6 days ago, **pr status to review**
   - under review

#### SIMPLE-ROBOTICS/CANDLEWICK
- [#31 https://github.com/Simple-Robotics/candlewick/pull/31](https://github.com/Simple-Robotics/candlewick/pull/31)
    - created 4 days ago

### PR merged within the week

#### COAL-LIBRARY/COAL

- [#681 Remove doxygen version constraint](https://github.com/coal-library/coal/pull/681)
   - created 7 days ago
- [#684 Update pixi lockfile](https://github.com/coal-library/coal/pull/684)
   - created 6 days ago
- [#687 Macros: fix coal assert](https://github.com/coal-library/coal/pull/687)
   - created 5 days ago
- [#686 Specify submodule branches](https://github.com/coal-library/coal/pull/686)
   - created 5 days ago

#### STACK-OF-TASKS/EIGENPY

- [#540 Update pixi lockfile](https://github.com/stack-of-tasks/eigenpy/pull/540)
   - created 6 days ago
- [#541 flake.lock: Update](https://github.com/stack-of-tasks/eigenpy/pull/541)
   - created 4 days ago
- [#538 Fix issue for sparse matrix conversions](https://github.com/stack-of-tasks/eigenpy/pull/538)
   - created 12 days ago
   - fixed issue with order of internal indices of sparse matrices (discrepencies between scipy and eigen)

#### STACK-OF-TASKS/PINOCCHIO

- [#2630 Update README.md for new minimal C++ version](https://github.com/stack-of-tasks/pinocchio/pull/2630)
   - created 7 days ago
- [#2631 Update pixi lockfile](https://github.com/stack-of-tasks/pinocchio/pull/2631)
   - created 6 days ago
- [#2633 Update readme](https://github.com/stack-of-tasks/pinocchio/pull/2633)
   - created 5 days ago
   - add core-dev team
- [#2636 Sync submodule CMake](https://github.com/stack-of-tasks/pinocchio/pull/2636)
   - created 3 days ago
- [#2637 Add CRBA CasADi example](https://github.com/stack-of-tasks/pinocchio/pull/2637)
   - created 3 days ago
   - Add example after comment from user
- [#2638 flake.lock: Update](https://github.com/stack-of-tasks/pinocchio/pull/2638)
   - created 2 days ago
- [#2639 build(deps): bump prefix-dev/setup-pixi from 0.8.3 to 0.8.4](https://github.com/stack-of-tasks/pinocchio/pull/2639)
   - created 0 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#282 Update pixi lockfile](https://github.com/Simple-Robotics/aligator/pull/282)
   - created 6 days ago
- [#283 [gar] Rename {LQRKnot,LQRProblem} to {LqrKnot, LqrProblem}](https://github.com/Simple-Robotics/aligator/pull/283)
   - created 6 days ago
   - split of PR still open
- [#284 Correct references to equations.](https://github.com/Simple-Robotics/aligator/pull/284)
   - created 4 days ago

#### SIMPLE-ROBOTICS/PROXSUITE-NLP

- [#128 Update pixi lockfile](https://github.com/Simple-Robotics/proxsuite-nlp/pull/128)
   - created 6 days ago

#### SIMPLE-ROBOTICS/NANOEIGENPY

- [#6 Add BSD-3 Clause license](https://github.com/Simple-Robotics/nanoeigenpy/pull/6)
   - created 10 days ago
- [#7 Add package.xml](https://github.com/Simple-Robotics/nanoeigenpy/pull/7)
   - created 7 days ago
- [#8 Add Accelerate support to pixi](https://github.com/Simple-Robotics/nanoeigenpy/pull/8)
   - created 5 days ago

#### SIMPLE-ROBOTICS/CANDLEWICK

- [#28 [cmake] slight refactor of examples listfile, update README](https://github.com/Simple-Robotics/candlewick/pull/28)
    - merged 3 days ago
- [#29 [examples] rename Python examples, check for in go2 example](https://github.com/Simple-Robotics/candlewick/pull/29)
    - merged 3 days ago
- [#30 Add Python example to load robot descriptions](https://github.com/Simple-Robotics/candlewick/pull/30)
    - merged 3 days ago
    - nice PR from Stéphane :)
- [#32 README : add pre-commit ci badge](https://github.com/Simple-Robotics/candlewick/pull/32)
    - merged 3 days ago
- [#33 [core] use C++20 <source_location> to replace error macros](https://github.com/Simple-Robotics/candlewick/pull/33)
    - merged 3 days ago

## 2025-03-31

### News

- [name=Joris] [Release d'aligator 0.12.0](https://github.com/Simple-Robotics/aligator/releases/tag/v0.12.0)
    - Minor release for compatibility with crocodyl v3.0.1
    - Possibly one of the last release ensuring this compatibility

### Technical discussions

- [name=Joris] Archivage de proxsuite-nlp et fusion avec aligator
    - proxsuite-nlp contained the manifold, non-linear strategy of aligator. Constraint in proxsuite-nlp defined by a function + operators
    - keeping proxsuite-nlp makes less sense due to interoperability
    - fuse proxsuite-nlp with aligator (not as subproject to avoid adding complexity). Message in README, archive repository and fuse
- [name=Guilhem] [keep-sorted](https://github.com/google/keep-sorted)
    - ordering lines and block of codes
    - could be used to handle large list of sources in CMake files
    - not yet tested
    - simplify the GH table of content in README
- [name=Joris] Génération de TOC sur github
    - Voir plutôt [mdBook](https://rust-lang.github.io/mdBook/)
    - Sphinx ?


### PR to review

#### COAL-LIBRARY/COAL

- [#527 Hide qhullcpp symbol](https://github.com/coal-library/coal/pull/527)
   - created 420 days ago, updated 21 days ago, **pr status wip**
   - no progress yet
- [#658 add BUILD_ONLY_PYTHON_INTERFACE option](https://github.com/coal-library/coal/pull/658)
   - created 46 days ago, updated 24 days ago, **pr status wip**
   - no progress yet
- [#659 Introduce next-generation Python bindings using `nanobind`](https://github.com/coal-library/coal/pull/659)
   - created 42 days ago, updated 7 days ago, **pr status wip**
   - work on nanoeigenpy has been addressed first
- [#660 Split python build into a specific sub project](https://github.com/coal-library/coal/pull/660)
   - created 40 days ago, updated 5 days ago, **pr status wip**
   - compile separately code / binding
   - required plenty of small changes with regards to BUILD_ONLY_PYTHON_INTERFACE
   - TODO : apply same structure on tests

#### STACK-OF-TASKS/EIGENPY

- [#370 example: custom numeric type](https://github.com/stack-of-tasks/eigenpy/pull/370)
   - created 683 days ago, updated 24 days ago, **pr status wip**
- [#538 Fix issue for sparse matrix conversions](https://github.com/stack-of-tasks/eigenpy/pull/538)
   - created 5 days ago, updated 5 days ago
   - Wilson noticed sparse matrices are not ordered
   - Fixed since eigen-3.4.90 (fix indices)
   - Status of the Eigen project maintenance raises questions
   - Copy the scipy.sparse_matrix and sort the indicies

#### STACK-OF-TASKS/PINOCCHIO

- [#2411 Momentum regressor](https://github.com/stack-of-tasks/pinocchio/pull/2411)
   - created 203 days ago, updated 14 days ago, **pr status wip**
- [#2421 Passivity-based RNEA Algorithms](https://github.com/stack-of-tasks/pinocchio/pull/2421)
   - created 195 days ago, updated 24 days ago, **pr status to review**
- [#2551 Implement Eigen-like expression templates for spatial algebra computations](https://github.com/stack-of-tasks/pinocchio/pull/2551)
   - created 81 days ago, updated 24 days ago, **pr status wip**
- [#2572 New header convention](https://github.com/stack-of-tasks/pinocchio/pull/2572)
   - created 48 days ago, updated 24 days ago, **pr status wip**
   - Required for pinocchio-v4
- [#2576 [cmake] Change formatting of listfiles to use gersemi, remove cmake-format](https://github.com/stack-of-tasks/pinocchio/pull/2576)
   - created 47 days ago, updated 24 days ago, **pr status wip**
- [#2617 Fix hpp-fcl dependency](https://github.com/stack-of-tasks/pinocchio/pull/2617)
   - created 17 days ago, updated 7 days ago, **pr status wip**
   - check who leads on this one (Joris when he gets back)

#### SIMPLE-ROBOTICS/ALIGATOR

- [#243 Add memory allocator support for LQ subproblem types, merge `gar` into main aligator library, rename `LQRKnot` and `LQRProblem`, slight refactor of `DenseRiccatiSolver`](https://github.com/Simple-Robotics/aligator/pull/243)
   - created 150 days ago, updated 4 days ago, **pr status wip**
   - PR just rebased

#### SIMPLE-ROBOTICS/PROXSUITE

- [#387 [WIP] OSQP](https://github.com/Simple-Robotics/proxsuite/pull/387)
   - created 12 days ago, updated 7 days ago, **pr status to review**
   - Tests were failing, review would be needed now


### PR merged within the week

#### COAL-LIBRARY/COAL

- [#675 PyPI: coal-library -> coal](https://github.com/coal-library/coal/pull/675)
   - created 7 days ago
- [#676 README/CHANGELOG: updates for hpp-fcl -> coal](https://github.com/coal-library/coal/pull/676)
   - created 7 days ago
- [#678 Fix doc parsing via doxygen scripts](https://github.com/coal-library/coal/pull/678)
   - created 5 days ago
   - versions doxygen was supposed to be < 1.13
   - this PR should allow to remove the guard

#### STACK-OF-TASKS/EIGENPY

- [#537 Update ROS CI](https://github.com/stack-of-tasks/eigenpy/pull/537)
   - created 14 days ago

#### STACK-OF-TASKS/PINOCCHIO

- [#2624 Fix ModelTpl::check() link](https://github.com/stack-of-tasks/pinocchio/pull/2624)
   - created 11 days ago
- [#2627 Fix PCH and ccache build](https://github.com/stack-of-tasks/pinocchio/pull/2627)
   - created 10 days ago

#### SIMPLE-ROBOTICS/ALIGATOR

- [#278 croco v3: boost -> std pointers](https://github.com/Simple-Robotics/aligator/pull/278)
   - created 10 days ago



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
