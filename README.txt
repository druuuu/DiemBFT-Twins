Implementation of DiemBFT v4: Machine Replication in the Diem Blockchain. proposed by the Diem team, in DistAlgo

PLATFORM:


The software platforms that are used in testing the algorithm are:


OS: 
macOS 11.6 (Big Sur) 
Windows 10


Python Implementation:
CPython


Python Versions used to test:
Python 3.6.13
Python 3.7.0
Python 3.7.12


DistAlgo Version used for implementation:
1.1.0b15


Type of host:
Laptop


WORKLOAD GENERATION:

TODO: Change this
We have specified the configuration that is required in a config file and placed it in a folder and named it as config. This folder consists of many such config files which are configured differently which would simulate the real case scenarios. These files are read by the main process which spawns the specified number of validators, clients, and also takes in the parameters which are required to simulate a real case scenario. These validators and clients run their own processes and communicate with each other which would essentially lead to a consensus of ordering the transactions and finalizing those.


The main file which controls the creation of validators and clients is run_diembft.da which is specified in the src folder. This file takes in the different workload configurations that are specified in the config.da file which is in the config folder. Run_diembft.da file after taking in the specified workload spawns the specified number of validators and clients. The client.da file specified in the src folder manages the workloads of all the spawned clients. This client.da file spawns the number of clients specified in the config file. The config file also specifies the number of client requests that the client needs to pass to the validators, the time that it needs to wait in between passing two requests, and the time that it needs to wait before retransmitting a request if it has not been received acknowledgment for a specific request. All the validators when they execute the request sent by the client will pass the response as an acknowledgment back to the client. By this, the client can verify that the request has been successfully executed.


TIMEOUTS:
The timeout formula is computed as 4*delta where delta is the highest time it took for a single round.


BUGS AND LIMITATIONS:
-- Sync up of validators is not possible
–- Depending on the system processing performance, the value of delta(highest time for executing one round) can change. Adjust the value of delta depending on the delta


MAIN FILES:
-- Main Simulator: <path_of_project_folder>/src/client.da
-- Config: <path_of_project_folder>/config/config.da
-- Client: <path_of_project_folder>/src/client.da
-- Validator(Replica): <path_of_project_folder>/src/validator.da

-- Main Code for Test Generator: <path_of_project_folder>/src/ScenarioGenerator.py
-- Main Code for Test Executor: <path_of_project_folder>/src/scenario_executor.da


CODE SIZE:
1.  Non-blank Non-comment lines of code in complete codebase: 1833	(Total)
                                       	277	(Other - client, config, run_diembft)
                                       	1556 (Algorithm - DiemBFT + Twins)

    github.com/AlDanial/cloc v 1.82  T=46.09 s (0.5 files/s, 73.7 lines/s)
    -------------------------------------------------------------------------------
    Language                     files          blank        comment           code
    -------------------------------------------------------------------------------
    Python                          18            477           1080           1699
    JSON                             3              5              0            134
    -------------------------------------------------------------------------------
    SUM:                            21            482           1080           1833
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


3. About 80% of 510 are for the algorithm itself.


LANGUAGE FEATURE USAGE:
Our algorithm uses approximately 21 dictionary comprehensions, 11 set comprehensions, 6 list comprehensions, 3 await statements and about 5 receive handlers.

Our Twins implementation uses approximately
4 await statements and about
8 receive handlers.


CONTRIBUTIONS:

