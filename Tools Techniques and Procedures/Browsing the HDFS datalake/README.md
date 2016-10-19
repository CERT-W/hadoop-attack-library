Browsing the HDFS datalake
==========================

Description
-----------
WebHDFS offers REST API for users to access data on the HDFS filesystem using the HTTP protocol.  
The API allows to perform all [possible actions](http://hadoop.apache.org/docs/r2.7.2/hadoop-project-dist/hadoop-hdfs/WebHDFS.html) on the HDFS filesystem (view, create, modify, etc.).  
By default, if Kerberos authentication is not enabled, no credential is needed to request these services: only identification is needed using the `user.name` parameter.  
WebHDFS API are exposed on the following services:
 * HDFS DataNode WebUI on port 50075
 * HttpFS module on port 14000  

Another method for listing the content is to call the [`/listPaths/` URI on a NameNode](https://blog.cloudera.com/blog/2009/08/hadoop-default-ports-quick-reference/).  

`HDFSBrowser` has been developped to allow attackers to easily browse the HDFS filesystem using WebHDFS and HttpFS services. `HDFSBrowser` is able to request the different known methods. 

Usage
-----
The application consist of the following commands:  

```
$ python hdfsbrowser.py  -h
usage: hdfsbrowser.py [-h] [--port PORT] [-o OUTPUT_FILE] [--ssl]
                       [--target-uri TARGET_URI] [-r] [--root-path ROOT_PATH]
                       [-m {all,whdfs,httpfs}] [--time-out TIME_OUT]
                       [-d DEPTH] [--threads THREADS] [--proxy PROXY]
                       [--header HEADER]
                       host

 
     _   _____________ ___________                                 
    | | | |  _  \  ___/  ___| ___ \                                
    | |_| | | | | |_  \ `--.| |_/ /_ __ _____      _____  ___ _ __ 
    |  _  | | | |  _|  `--. \ ___ \ '__/ _ \ \ /\ / / __|/ _ \ '__|
    | | | | |/ /| |   /\__/ / |_/ / | | (_) \ V  V /\__ \  __/ |   
    \_| |_/___/ \_|   \____/\____/|_|  \___/ \_/\_/ |___/\___|_|  

    

positional arguments:
  host                  host

optional arguments:
  -h, --help            show this help message and exit
  --port PORT           HDFS port
  -o OUTPUT_FILE, --output-file OUTPUT_FILE
                        Write to file instead of stdout
  --ssl                 Try SSL/TLS
  --target-uri TARGET_URI
                        Target URI of the Hadoop installation
  -r, --recursive       Be recursive
  --root-path ROOT_PATH
                        Root path for the directory listing
  -m {all,whdfs,httpfs}, --method {all,whdfs,httpfs}
                        Method to use [
  --time-out TIME_OUT   Timeout for request
  -d DEPTH, --depth DEPTH
                        Recursion depth while listing directories
  --threads THREADS     Number of threads
  --proxy PROXY         Use proxy on given port
  --header HEADER       Pass custom header to server
```



