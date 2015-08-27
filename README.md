# BarycentricCluster

This is my implementation of the Barycentric Clustering (BC) algorithm in MapReduce, originally proposed by Cohen (http://csee.ogi.edu/~zak/cs506-pslc/barycentric.pdf). BC is a physics-based algorithm that uses the ball and spring model, in which a graph’s vertices are considered as balls and its edges as springs. According to Hooke’s Law, every spring exerts a force in direct proportion to the distance that it is stretched or compressed. If the ball and spring structure is initially stretched out and then released, balls that are mutually connected by many springs will naturally clump together. This notion can be used to identify clusters.

This program was written and tested in Hadoop version 2.7.0.

To compile:
$ hadoop com.sun.tools.javac.Main BC.java

This produces several .class files. Package them into a .jar file named bc.jar:
$ jar cf bc.jar BC*.class

To run the .jar file:
$ hadoop jar bc.jar BC arg0 arg1 arg2 arg3 arg4

arg0 = HDFS input location
arg1 = HDFS output location
arg2 = number of runs (use 1, unless the program needs to be run multiple times over and over again)
arg3 = number of vertices
arg4 = number of random starts (usually set to 30)
