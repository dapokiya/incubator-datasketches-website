---
layout: doc_page
---
<!--
    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
-->
## Key Features

### [Sketch Features Matrix]({{site.docs_dir}}/Architecture/SketchFeaturesMatrix.html)

### Common Sketch Properties

  * Please refer to the [Sketch Criteria]({{site.docs_dir}}/Architecture/SketchCriteria.html) for the criteria for sketches to be included in the library.
  * Query results are <b>approximate</b> but within well defined error bounds that are user 
  configurable by trading off sketch size with accuracy.
  * Designed for <a href="{{site.docs_dir}}/LargeScale.html">Large-scale</a> computing environments 
  that must handle <b>Big Data</b>.( e.g., 
<a href="https://hadoop.apache.org/">Hadoop</a>, 
<a href="https://pig.apache.org/">Pig</a>, 
<a href="https://hive.apache.org/">Hive</a>,
<a href="https://druid.io">Druid</a>,
<a href="https://spark.apache.org">Spark</a>), 
and are heavily used within Yahoo / Verizon-Media.
  * <b>Maven deployable</b> and registered with 
<a href="https://search.maven.org/#search|ga|1|DataSketches">The Central Repository</a>.
  * Comprehensive <b>unit tests</b> and testing tools are provided.
  * Extensive documentation with the systems developer in mind.

### Built-In, General Purpose Functions

  * General purpose <a href="{{site.docs_dir}}/Memory/MemoryPackage.html">Memory Package</a> for managing data off the Java Heap. 
This enables systems designers the ability to manage their own large data heaps with 
dedicated processor threads that would otherwise put undue pressure on the Java heap and 
its garbage collection.
  * General purpose implementaion of Austin Appleby's 128-bit MurmurHash3 algorithm, 
  with a number of useful extensions.

### Robust, High Quality Implementations.

  * Extensive test code leveraging <a href="https://testng.org">TestNG</a>.
  * Speed and accuracy performance characterization testing code 
  included in the <a href="https://github.com/DataSketches/sketches-misc">sketches-misc</a>  repository.
  * High Test Code coverage (
<a href="{{site.core_readme}}">Core</a>,
<a href="{{site.pig_readme}}">Pig</a>,
<a href="{{site.hive_readme}}">Hive</a>,) as measured by 
<a href="https://www.eclemma.org/jacoco/">JaCoCo</a> and published by 
<a href="https://coveralls.io">Coveralls</a>.
* Comprehensive Javadocs that satisfy 
<a href="https://www.oracle.com/technetwork/java/index.html">Java JDK8</a> standards.
* Suitable for production environments.

### Opportunities to Extend

* There is ample opportunity for interested parties to contribute additional algorithms in this exciting area.


## Key Algorithms

### Count Distinct / Count Unique

#### Solves Computational Challenges Associated with Unique Identifiers

  * <b>Estimating cardinality</b> of a stream with many duplicates
  * Performing <a href="{{site.docs_dir}}/Theta/ThetaSketchSetOps.html">set operations</a> (e.g., Union, Intersection, 
  and Difference) on sets of unique identifiers
  * Estimates of the <b>error bounds</b> of the result can be obtained directly from the result sketch
  * Two families of Count Unique algorithms:
    * <a href="{{site.docs_dir}}/Theta/ThetaSketchFramework.html">The Theta Sketch Framework</a> algorithms that are tuned 
    for operation on the java heap or off-heap.
    * <a href="{{site.docs_dir}}/HLL/HLL.html">The Hyper-Log Log algorithms</a> when sketch size is of utmost concern.
  
### Quantiles

  * Get normal or inverse PDFs or CDFs of the distributions of any numeric value from your raw data in a 
  single pass.
  * Well defined error bounds on the result.
  
### Frequent Items

  * Get the most frequent items from a stream of items.
  
### Tuple Sketch

  * Associative sketches that are useful for performing approximate join operations and 
  extracting other kinds of behavior associated with unique identifiers.
