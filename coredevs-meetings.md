# MAESTRO COREDEVS MEETING - Notes


# 2025-06-02

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
