# rstream
This is the RStream repo I created for our use.
https://github.com/chenxuhao/RStream.git

Before you build RStream, modify line 3 in Makefile to specify the path of Boost library.

I have generated the input files for RStream:

    /net/ohm/export/iss/inputs/mtx/RStream/citeseer.sadj
    /net/ohm/export/iss/inputs/mtx/RStream/pdb1.sadj
    /net/ohm/export/iss/inputs/mtx/RStream/mico.sadj
    /net/ohm/export/iss/inputs/mtx/RStream/patent_citations.sadj


You can run motif counting in RStream like this:

cd /net/ohm/export/iss/cxh/RStream

    $ ./bin/motif_count /net/ohm/export/iss/inputs/mtx/RStream/citeseer.sadj 1 3 1

bin/motif_count [input graph(adj list format)] [num of partitions] [size of motif] [num of threads]

The output should be like this:

    $ ./bin/motif_count /net/ohm/export/iss/inputs/mtx/RStream/citeseer.sadj 1 3 1


    =================================================== start preprocessing ===================================================
    start to convert adj list file...
    num_vertices = 3312
    maxVertexId = 3311, minVertexId = 0
    num_edges = 9072
    Reading /net/ohm/export/iss/inputs/mtx/RStream/citeseer.sadj.meta
    Input format: 1
    Number of vertices: 3312
    Number of partitions: 1
    Edge type: LabeledEdge
    Number of bytes per edge: 10
    Number of exec threads: 1
    Number of write threads: 1

    =================================================== finish preprocessing ===================================================
    Aggregation: num_threads = 1
    Aggregation: num_partitions = 1
    Aggregation: num_write_threads = 1


    =================================================== init ===================================================
    cxh: num_iterations = 3


    =================================================== Iteration 1 ===================================================

    ----------------------------------- joining -----------------------------------
    Number of tuples in update 1: 	26878
    Size of tuple: 	24
    u, 1, 26878, 24, 645072

    ----------------------------------- aggregating -----------------------------------
    a, 1, 1, 36, 36
    {{([1, 0, 0, 0, 0], [3, 0, 0, 0, 0], [2, 0, 0, 0, 1]); 3; 4110465937} --> 26878


    =================================================== Iteration 2 ===================================================

    ----------------------------------- joining -----------------------------------
    Number of tuples in update 2: 	1166
    Size of tuple: 	32
    u, 2, 1166, 32, 37312

    ----------------------------------- aggregating -----------------------------------
    a, 3, 1, 44, 44
    {{([1, 0, 0, 0, 0], [2, 0, 0, 0, 0], [3, 0, 0, 0, 0], [3, 0, 0, 0, 1]); 3; 227016548} --> 1166



    =================================================== cleaning ===================================================
    Error deleting file: No such file or directory
    Error deleting file: No such file or directory
    Error deleting file: No such file or directory
    Finish motif-counting. Running time : 0.208099 s


    ------------------------------ resource usage ------------------------------
    Wall time: 0 ms; 0.000 s; 0.000 m; 0.000 h
    CPU time: 359.917 ms; 0.360 s; 0.006 m; 0.000 h
    Peak memory: 13512.000 KB; 13.195 MB; 0.013 GB
    ------------------------------ resource usage ------------------------------
