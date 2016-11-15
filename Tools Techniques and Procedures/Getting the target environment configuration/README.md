Getting the target environment configuration
============================================

Description
-----------
This tutorial explains how to set up a correct environnement in order to perform an Hadoop pentest


-----------
Hadoop core
-----------


----------
Map-Reduce
----------


----
Yarn
----

`HadoopSnooper`has been developped to allow attackers to easily retrieve a suitable configuration using configuration files exposed through Hadoop HTTP interfaces.

Usage
-----
The application consist of the following commands:

```
$ python hadoopsnooper.py -h
usage: hadoopsnooper.py [-h] --nn NN [--dn DN] [-o OUTPUT_DIR] [--batch] host

    __  __          __                 _____                                  
   / / / /___ _____/ /___  ____  ____ / ___/____  ____  ____  ____  ___  _____
  / /_/ / __ `/ __  / __ \/ __ \/ __ \__ \/ __ \/ __ \/ __ \/ __ \/ _ \/ ___/
 / __  / /_/ / /_/ / /_/ / /_/ / /_/ /__/ / / / / /_/ / /_/ / /_/ /  __/ /    
/_/ /_/\__,_/\__,_/\____/\____/ .___/____/_/ /_/\____/\____/ .___/\___/_/     
                             /_/                          /_/                 
    

positional arguments:
  host                  host

optional arguments:
  -h, --help            show this help message and exit
  --nn NN               Cluster namenode (format: hdfs://namenode.hadoop:8020)
  --dn DN               Cluster datanodes addresses
  -o OUTPUT_DIR, --output-dir OUTPUT_DIR
                        Output directory
  --batch               Never ask for user input, use the default behaviour
