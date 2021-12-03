Implementation of DiemBFT v4: Machine Replication in the Diem Blockchain. proposed by the Diem team, in DistAlgo

PLATFORM:


The software platforms that are used in testing the algorithm are:


OS: 
macOS 11.6 (Big Sur) 
Windows 10


Python Implementation:
CPython


Python Versions used to test:
Python 3.7.12


DistAlgo Version used for implementation:
1.1.0b15


Type of host:
Laptop



BUGS AND LIMITATIONS:
–- Depending on the system processing performance and partition scenarios, the value of delta(highest time for executing one round) and liveness can change. Adjust the value of delta depending on the delta
-- cryptographic hash values are not validated at certain points.

MAIN FILES:
-- Main Simulator:
    Scenario Generation -  <path_of_project_folder>/src/ScenarioGenerator.da
    Scenario Execution -   <path_of_project_folder>/src/scenario_executor.da
                    
-- Config: <path_of_project_folder>/config/config.da
-- Network Playground: <path_of_project_folder>/src/network_playground.da
-- Validator(Replica): <path_of_project_folder>/src/validator.da

CODE SIZE:
1.  Non-blank Non-comment lines of code in complete codebase: 2089	(Total)
                                       	277	(Other - client, config, run_diembft)
                                       	1,812 (Algorithm - DiemBFT + Twins)

    github.com/AlDanial/cloc v 1.82  T=46.09 s (0.5 files/s, 73.7 lines/s)
    -------------------------------------------------------------------------------
    Language                     files          blank        comment           code
    -------------------------------------------------------------------------------
    Python                          16            485            691           1971
    JSON                             1              1              0            118
    -------------------------------------------------------------------------------
    SUM:                            17            486            691           2089
    -------------------------------------------------------------------------------


    Files added for Twins implementation:
        scenario_executor.da
        ScenarioGenerator.py
        network_playground.da
        config_test_generator.py

    Non-blank Non-comment lines of code in Twins implementation files: 510

    github.com/AlDanial/cloc v 1.82  T=100.23 s (0.0 files/s, 9.4 lines/s)
    -------------------------------------------------------------------------------
    Language                     files          blank        comment           code
    -------------------------------------------------------------------------------
    Python                           4            164            264            510
    -------------------------------------------------------------------------------
    SUM:                             4            164            264            510
    -------------------------------------------------------------------------------


2. Count was obtained using commands:
    cloc command - cloc --force-lang="Python",da .
    cloc command - cloc --force-lang="Python",da network_playground.da scenario_executor.da ScenarioGenerator.py config_test_generator.py


3. About % of 510 are for the algorithm itself.


LANGUAGE FEATURE USAGE:
Our algorithm uses approximately 28 dictionary comprehensions, 14 set comprehensions, 7 list comprehensions, 15 await statements and about 20 receive handlers.

Our Twins implementation uses approximately
7 list comprehensions
6 await statements and about
12 receive handlers.


CONTRIBUTIONS:
All members have contributed equally. Special contributions:
Aditya Bhide: scenario generator
Niket Shah : scenario executor and sync up
Drushti Mewada: network Playground
