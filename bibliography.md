# Introduction #

This bibliography is intended as a resource for people writing papers that refer to the
Google cluster traces.  It is intended to cover papers that analyze the traces,
as well as ones that use them as inputs to other studies.

  * It's recommended to `\usepackage{url`}.
  * Entries are in publication-date order, with the most recent at the top.
  * Items in **bold** are the recommended citations.
  * Bibtex ignores stuff that is outside the entries, so it's safe to copy and save the entire contents as a .bib file.

# Trace-announcements #

These entries can be used to cite the traces themselves.
The first couple are for the May 2011 "full" trace.
```
@Misc{clusterdata:Wilkes2011,
  author = {John Wilkes},
  title = {More {Google} cluster data},
  howpublished = {Google research blog},
  month = Nov,
  year = 2011,
  note = {Posted at
	\url{http://googleresearch.blogspot.com/2011/11/more-google-cluster-data.html}.},
}
```

```
@TechReport{clusterdata:Reiss2011,
  author = {Charles Reiss and John Wilkes and Joseph L. Hellerstein},
  title = {{Google} cluster-usage traces: format + schema},
  institution = {Google Inc.},
  year = 2011,
  month = Nov,
  type = {Technical Report},
  address = {Mountain View, CA, USA},
  note = {Revised 2012.03.20.  Posted at
	\url{http://code.google.com/p/googleclusterdata/wiki/TraceVersion2}},
}
```

The second one is for the earlier "small" 7-hour trace.
```
@Misc{clusterdata:Hellersetein2010,
  author = {Joseph L. Hellerstein},
  title = {{Google} cluster data},
  howpublished = {Google research blog},
  month = Jan,
  year = 2010,
  note = {Posted at \url{http://googleresearch.blogspot.com/2010/01/google-cluster-data.html}.},
}
```

The next paper describes the policy choices and technologies used to
make the traces safe to release.
```
@InProceedings{clusterdata:Reiss2012,
  author = {Charles Reiss and John Wilkes and Joseph L. Hellerstein},
  title = {Obfuscatory obscanturism: making workload traces of
	commercially-sensitive systems safe to release},
  year = 2012,
  booktitle = {3rd International Workshop on Cloud Management (CLOUDMAN)},
  month = Apr,
  publisher = {IEEE},
  pages = {1279--1286},
  address = {Maui, HI, USA},
  abstract = {Cloud providers such as Google are interested in fostering
	research on the daunting technical challenges they face in
	supporting planetary-scale distributed systems, but no
	academic organizations have similar scale systems on which to
	experiment. Fortunately, good research can still be done using
	traces of real-life production workloads, but there are risks
	in releasing such data, including inadvertently disclosing
	confidential or proprietary information, as happened with the
	Netflix Prize data. This paper discusses these risks, and our
	approach to them, which we call systematic obfuscation. It
	protects proprietary and personal data while leaving it
	possible to answer interesting research questions. We explain
	and motivate some of the risks and concerns and propose how
	they can best be mitigated, using as an example our recent
	publication of a month-long trace of a production system
	workload on a 11k-machine cluster.},
  url = {http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=6212064},
}
```

# Trace-analysis papers #

These papers are primarily about analyzing the traces.
**If you just want one citation, then `\cite{clusterdata:Reiss2012b}` is recommended.**
Order: most recent first.

```
@INPROCEEDINGS{clusterdata:Abdul-Rahman2014,
  author = {Abdul-Rahman, Omar Arif and Aida, Kento},
  title = {Towards understanding the usage behavior of {Google} cloud
	users: the mice and elephants phenomenon},
  booktitle = {IEEE International Conference on Cloud Computing
	Technology and Science (CloudCom)},
  year = 2014,
  month = dec,
  address = {Singapore},
  pages = {272--277},
  keywords = { Google trace; Workload trace analysis; User session
	view; Application composition; Mass-Count disparity;
	Exploratory statistical analysis; Visual analysis;
	Color-schemed graphs; Coarse grain classification;
	Heavy-tailed distributions; Long-tailed lognormal
	distributions; Exponential distribution; Normal distribution;
	Discrete modes; Large web services; Batch processing;
	MapReduce computation; Human users; },
  abstract = {In the era of cloud computing, users encounter the
	challenging task of effectively composing and running their
	applications on the cloud. In an attempt to understand user
	behavior in constructing applications and interacting with
	typical cloud infrastructures, we analyzed a large utilization
	dataset of Google cluster. In the present paper, we consider
	user behavior in composing applications from the perspective
	of topology, maximum requested computational resources, and
	workload type. We model user dynamic behavior around the
	user's session view. Mass-Count disparity metrics are used to
	investigate the characteristics of underlying statistical
	models and to characterize users into distinct groups
	according to their composition and behavioral classes and
	patterns. The present study reveals interesting insight into
	the heterogeneous structure of the Google cloud workload.},
  doi = {10.1109/CloudCom.2014.75},
}
```

```
@inproceedings{clusterdata:Di2013,
  title = {Characterizing cloud applications on a {Google} data center},
  author = {Di, Sheng and Kondo, Derrick and Franck, Cappello},
  booktitle = {42nd International Conference on Parallel Processing (ICPP)},
  year = 2013,
  month = Oct,
  address = {Lyon, France},
  abstract = {In this paper, we characterize Google applications,
	based on a one-month Google trace with over 650k jobs running
	across over 12000 heterogeneous hosts from a Google data
	center. On one hand, we carefully compute the valuable
	statistics about task events and resource utilization for
	Google applications, based on various types of resources (such
	as CPU, memory) and execution types (e.g., whether they can
	run batch tasks or not). Resource utilization per application
	is observed with an extremely typical Pareto principle. On the
	other hand, we classify applications via a K-means clustering
	algorithm with optimized number of sets, based on task events
	and resource usage. The number of applications in the Kmeans
	clustering sets follows a Pareto-similar distribution. We
	believe our work is very interesting and valuable for the
	further investigation of Cloud environment.},
}
```

```
@INPROCEEDINGS{clusterdata:Reiss2012b,
  title = {Heterogeneity and dynamicity of clouds at scale: {Google}
	trace analysis},
  author = {Charles Reiss and Alexey Tumanov and Gregory R. Ganger and
	Randy H. Katz and Michael A. Kozuch},
  booktitle = {ACM Symposium on Cloud Computing (SoCC)},
  year = 2012,
  month = Oct,
  address = {San Jose, CA, USA},
  abstract = {To better understand the challenges in developing
	effective cloud-based resource schedulers, we analyze the
	first publicly available trace data from a sizable
	multi-purpose cluster.  The most notable workload
	characteristic is heterogeneity: in resource types (e.g.,
	cores:RAM per machine) and their usage (e.g., duration and
	resources needed). Such heterogeneity reduces the
	effectiveness of traditional slot- and core-based scheduling.
	Furthermore, some tasks are constrained as to the kind of
	machine types they can use, increasing the complexity of
	resource assignment and complicating task migration. The
	workload is also highly dynamic, varying over time and most
	workload features, and is driven by many short jobs that
	demand quick scheduling decisions.  While few simplifying
	assumptions apply, we find that many longer-running jobs have
	relatively stable resource utilizations, which can help
	adaptive resource schedulers.},
  url = {http://www.pdl.cmu.edu/PDL-FTP/CloudComputing/googletrace-socc2012.pdf},
  privatenote = {An earlier version of this was posted at
	\url{http://www.istc-cc.cmu.edu/publications/papers/2012/ISTC-CC-TR-12-101.pdf},
	and included here as clusterdata:Reiss2012a. Please use this
	version instead of that.},
}
```

```
@INPROCEEDINGS{clusterdata:Liu2012,
  author = {Zitao Liu and Sangyeun Cho},
  title = {Characterizing machines and workloads on a {Google} cluster},
  booktitle = {8th International Workshop on Scheduling and Resource
	Management for Parallel and Distributed Systems (SRMPDS)},
  year = 2012,
  month = Sep,
  address = {Pittsburgh, PA, USA},
  abstract = {Cloud computing offers high scalability, flexibility and
	cost-effectiveness to meet emerging computing
	requirements. Understanding the characteristics of real
	workloads on a large production cloud cluster benefits not
	only cloud service providers but also researchers and daily
	users.  This paper studies a large-scale Google cluster usage
	trace dataset and characterizes how the machines in the
	cluster are managed and the workloads submitted during a
	29-day period behave. We focus on the frequency and pattern of
	machine maintenance events, job- and task-level workload
	behavior, and how the overall cluster resources are utilized.},
  url = {http://www.cs.pitt.edu/cast/abstract/liu-srmpds12.html},
}
```

```
@INPROCEEDINGS{clusterdata:Di2012a,
  author = {Sheng Di and Derrick Kondo and Walfredo Cirne},
  title = {Characterization and comparison of cloud versus {Grid} workloads},
  booktitle = {International Conference on Cluster Computing (IEEE CLUSTER)},
  year = 2012,
  month = Sep,
  pages = {230--238},
  address = {Beijing, China},
  abstract = {A new era of Cloud Computing has emerged, but the
	characteristics of Cloud load in data centers is not perfectly
	clear. Yet this characterization is critical for the design of
	novel Cloud job and resource management systems. In this
	paper, we comprehensively characterize the job/task load and
	host load in a real-world production data center at Google
	Inc. We use a detailed trace of over 25 million tasks across
	over 12,500 hosts. We study the differences between a Google
	data center and other Grid/HPC systems, from the perspective
	of both work load (w.r.t. jobs and tasks) and host load
	(w.r.t. machines). In particular, we study the job length, job
	submission frequency, and the resource utilization of jobs in
	the different systems, and also investigate valuable
	statistics of machine's maximum load, queue state and relative
	usage levels, with different job priorities and resource
	attributes. We find that the Google data center exhibits finer
	resource allocation with respect to CPU and memory than that
	of Grid/HPC systems. Google jobs are always submitted with
	much higher frequency and they are much shorter than Grid
	jobs. As such, Google host load exhibits higher variance and
	noise.},
  keywords = {cloud computing;computer centres;grid computing;queueing
	theory;resource allocation;search engines;CPU;Google data
	center;cloud computing;cloud job;cloud load;data centers;grid
	workloads;grid-HPC systems;host load;job length;job submission
	frequency;jobs resource utilization;machine maximum load;queue
	state;real-world production data center;relative usage
	levels;resource allocation;resource attributes;resource
	management systems;task load;Capacity
	planning;Google;Joints;Load modeling;Measurement;Memory
	management;Resource management;Cloud Computing;Grid
	Computing;Load Characterization},
  doi = {10.1109/CLUSTER.2012.35},
  privatenote = {An earlier version is available at
	\url{http://hal.archives-ouvertes.fr/hal-00705858}.  It used
	to be included here as clusterdata:Di2012.},
}
```

```
@Article{clusterdata:Mishra2010,
  author = {Mishra, Asit K. and Hellerstein, Joseph L. and Cirne,
	Walfredo and Das, Chita R.},
  title = {Towards characterizing cloud backend workloads: insights
	from {Google} compute clusters},
  journal = {SIGMETRICS Perform. Eval. Rev.},
  volume = {37},
  number = {4},
  month = Mar,
  year = 2010,
  issn = {0163-5999},
  pages = {34--41},
  numpages = {8},
  url = {http://doi.acm.org/10.1145/1773394.1773400},
  doi = {10.1145/1773394.1773400},
  publisher = {ACM},
  abstract = {The advent of cloud computing promises highly available,
	efficient, and flexible computing services for applications
	such as web search, email, voice over IP, and web search
	alerts. Our experience at Google is that realizing the
	promises of cloud computing requires an extremely scalable
	backend consisting of many large compute clusters that are
	shared by application tasks with diverse service level
	requirements for throughput, latency, and jitter. These
	considerations impact (a) capacity planning to determine which
	machine resources must grow and by how much and (b) task
	scheduling to achieve high machine utilization and to meet
	service level objectives.

	Both capacity planning and task scheduling require a good
	understanding of task resource consumption (e.g., CPU and
	memory usage). This in turn demands simple and accurate
	approaches to workload classification-determining how to form
	groups of tasks (workloads) with similar resource demands. One
	approach to workload classification is to make each task its
	own workload. However, this approach scales poorly since tens
	of thousands of tasks execute daily on Google compute
	clusters. Another approach to workload classification is to
	view all tasks as belonging to a single
	workload. Unfortunately, applying such a coarse-grain workload
	classification to the diversity of tasks running on Google
	compute clusters results in large variances in predicted
	resource consumptions.

	This paper describes an approach to workload classification
	and its application to the Google Cloud Backend, arguably the
	largest cloud backend on the planet. Our methodology for
	workload classification consists of: (1) identifying the
	workload dimensions; (2) constructing task classes using an
	off-the-shelf algorithm such as k-means; (3) determining the
	break points for qualitative coordinates within the workload
	dimensions; and (4) merging adjacent task classes to reduce
	the number of workloads. We use the foregoing, especially the
	notion of qualitative coordinates, to glean several insights
	about the Google Cloud Backend: (a) the duration of task
	executions is bimodal in that tasks either have a short
	duration or a long duration; (b) most tasks have short
	durations; and (c) most resources are consumed by a few tasks
	with long duration that have large demands for CPU and
	memory.},
}
```


---


# Trace-usage papers #

These entries are for papers that primarily focus on some other topic, but
use the traces as inputs, e.g., in simulations or load predictions.
Order: most recent first.

```
@INPROCEEDINGS{clusterdata:Sirbu2015,
  title = {Towards Data-Driven Autonomics in Data Centers},
  author = {Alina S{\^\i}rbu and Ozalp Babaoglu},
  booktitle = {International Conference on Cloud and Autonomic Computing (ICCAC)},
  month = Sep,
  year = 2015,
  address = {Cambridge, MA, USA},
  publisher = {IEEE Computer Society},
  keywords = {Data science; predictive analytics; Google cluster
	trace; log data analysis; failure prediction; machine learning
	classification; ensemble classifier; random forest; BigQuery},
  abstract = {Continued reliance on human operators for managing data
	centers is a major impediment for them from ever reaching
	extreme dimensions.  Large computer systems in general, and
	data centers in particular, will ultimately be managed using
	predictive computational and executable models obtained
	through data-science tools, and at that point, the
	intervention of humans will be limited to setting high-level
	goals and policies rather than performing low-level
	operations. Data-driven autonomics, where management and
	control are based on holistic predictive models that are built
	and updated using generated data, opens one possible path
	towards limiting the role of operators in data centers.  In
	this paper, we present a data-science study of a public Google
	dataset collected in a 12K-node cluster with the goal of
	building and evaluating a predictive model for node failures.
	We use BigQuery, the big data SQL platform from the Google
	Cloud suite, to process massive amounts of data and generate a
	rich feature set characterizing machine state over time. We
	describe how an ensemble classifier can be built out of many
	Random Forest classifiers each trained on these features, to
	predict if machines will fail in a future 24-hour window. Our
	evaluation reveals that if we limit false positive rates to
	5\%, we can achieve true positive rates between 27\% and 88\%
	with precision varying between 50\% and 72\%.  We discuss the
	practicality of including our predictive model as the central
	component of a data-driven autonomic manager and operating it
	on-line with live data streams (rather than off-line on data
	logs).  All of the scripts used for BigQuery and
	classification analyses are publicly available from the
	authors' website.},
  url = {http://www.cs.unibo.it/babaoglu/papers/pdf/CAC2015.pdf},
}
```

```
@InProceedings{clusterdata:Iglesias2014:task-estimation,
  author = {Jesus Omana Iglesias and Liam Murphy Lero and Milan De
	Cauwer and Deepak Mehta and Barry O'Sullivan},
  title = {A methodology for online consolidation of tasks through
	more accurate resource estimations},
  year = 2014,
  month = Dec,
  booktitle = {IEEE/ACM Intl. Conf. on Utility and Cloud Computing (UCC)},
  address = {London, UK},
  abstract = {Cloud providers aim to provide computing services for a
	wide range of applications, such as web applications, emails,
	web searches, and map reduce jobs. These applications are
	commonly scheduled to run on multi-purpose clusters that
	nowadays are becoming larger and more heterogeneous. A major
	challenge is to efficiently utilize the cluster's available
	resources, in particular to maximize overall machine
	utilization levels while minimizing application waiting
	time. We studied a publicly available trace from a large
	Google cluster ($\sim$12,000 machines) and observed that users
	generally request more resources than required for running
	their tasks, leading to low levels of utilization.  In this
	paper, we propose a methodology for achieving an efficient
	utilization of the cluster's resources while providing the
	users with fast and reliable computing services. The
	methodology consists of three main modules: i) a prediction
	module that forecasts the maximum resource requirement of a
	task; ii) a scalable scheduling module that efficiently
	allocates tasks to machines; and iii) a monitoring module that
	tracks the levels of utilization of the machines and tasks. We
	present results that show that the impact of more accurate
	resource estimations for the scheduling of tasks can lead to
	an increase in the average utilization of the cluster, a
	reduction in the number of tasks being evicted, and a
	reduction in task waiting time.},
  keys = {online scheduling, Cloud computing, forecasting, resource provisioning,
constraint programming},
}
```

```
@InProceedings{clusterdata:Balliu2014,
  author = {Alkida Balliu and Dennis Olivetti and Ozalp Babaoglu and
	Moreno Marzolla and Alina Sirbu},
  title = {{BiDAl: Big Data Analyzer} for cluster traces},
  year = 2014,
  booktitle = {Informatik Workshop on System Software Support for Big Data (BigSys)},
  month = Sep,
  publisher = {GI-Edition Lecture Notes in Informatics},
  abstract = { Modern data centers that provide Internet-scale
	services are stadium-size structures housing tens of thousands
	of heterogeneous devices (server clusters, networking
	equipment, power and cooling infrastructures) that must
	operate continuously and reliably.  As part of their
	operation, these devices produce large amounts of data in the
	form of event and error logs that are essential not only for
	identifying problems but also for improving data center
	efficiency and management. These activities employ data
	analytics and often exploit hidden statistical patterns and
	correlations among different factors present in the data.
	Uncovering these patterns and correlations is challenging due
	to the sheer volume of data to be analyzed. This paper
	presents BiDAl, a prototype ``log-data analysis framework''
	that incorporates various Big Data technologies to simplify
	the analysis of data traces from large clusters. BiDAl is
	written in Java with a modular and extensible architecture so
	that different storage backends (currently, HDFS and SQLite
	are supported), as well as different analysis languages
	(current implementation supports SQL, R and Hadoop MapReduce)
	can be easily selected as appropriate. We present the design
	of BiDAl and describe our experience using it to analyze
	several public traces of Google data clusters for building a
	simulation model capable of reproducing observed behavior.},
}
```

```
@inproceedings{clusterdata:Caglar2014,
  title = {{iOverbook}: intelligent resource-overbooking to support
	soft real-time applications in the cloud},
  author = {Faruk Caglar and Aniruddha Gokhale},
  booktitle = {7th IEEE International Conference on Cloud Computing (IEEE CLOUD)},
  year = 2014,
  month = {Jun--Jul},
  address = {Anchorage, AK, USA},
  abstract = { Cloud service providers (CSPs) often overbook their
	resources with user applications despite having to maintain
	service-level agreements with their customers. Overbooking is
	attractive to CSPs because it helps to reduce power
	consumption in the data center by packing more user jobs in
	less number of resources while improving their
	profits. Overbooking becomes feasible because user
	applications tend to overestimate their resource requirements
	utilizing only a fraction of the allocated
	resources. Arbitrary resource overbooking ratios, however, may
	be detrimental to soft real-time applications, such as airline
	reservations or Netflix video streaming, which are
	increasingly hosted in the cloud. The changing dynamics of the
	cloud preclude an offline determination of overbooking
	ratios. To address these concerns, this paper presents
	iOverbook, which uses a machine learning approach to make
	systematic and online determination of overbooking ratios such
	that the quality of service needs of soft real-time systems
	can be met while still benefiting from
	overbooking. Specifically, iOverbook utilizes historic data of
	tasks and host machines in the cloud to extract their resource
	usage patterns and predict future resource usage along with
	the expected mean performance of host machines. To evaluate
	our approach, we have used a large usage trace made available
	by Google of one of its production data centers. In the
	context of the traces, our experiments show that iOverbook can
	help CSPs improve their resource utilization by an average of
	12.5\% and save 32\% power in the data center.},
  url = {http://www.dre.vanderbilt.edu/~gokhale/WWW/papers/CLOUD-2014.pdf},
}
```

```
@inproceedings{clusterdata:Sebastio2014,
  author = {Sebastio, Stefano and Amoretti, Michele and Lluch Lafuente, Alberto},
  title = {A computational field framework for collaborative task
	execution in volunteer clouds},
  booktitle = {International Symposium on Software Engineering for
	Adaptive and Self-Managing Systems (SEAMS)},
  year = 2014,
  month = Jun,
  isbn = {978-1-4503-2864-7},
  address = {Hyderabad, India},
  pages = {105--114},
  url = {http://doi.acm.org/10.1145/2593929.2593943},
  doi = {10.1145/2593929.2593943},
  publisher = {ACM},
  keywords = {ant colony optimization, bio-inspired algorithms, cloud
	computing, distributed tasks execution, peer-to-peer, self-*
	systems, spatial computing, volunteer computing},
  abstract = {The increasing diffusion of cloud technologies offers
	new opportunities for distributed and collaborative
	computing. Volunteer clouds are a prominent example, where
	participants join and leave the platform and collaborate by
	sharing computational resources. The high complexity, dynamism
	and unpredictability of such scenarios call for decentralized
	self-* approaches. We present in this paper a framework for
	the design and evaluation of self-adaptive collaborative task
	execution strategies in volunteer clouds.  As a byproduct, we
	propose a novel strategy based on the Ant Colony Optimization
	paradigm, that we validate through simulation-based
	statistical analysis over Google cluster data.},
}
```

```
@inproceedings{clusterdata:Breitgand2014-adaptive,
  title = {An adaptive utilization accelerator for virtualized environments},
  author = {Breitgand, David and Dubitzky, Zvi and Epstein, Amir and
	Feder, Oshrit and Glikson, Alex and Shapira, Inbar and
	Toffetti, Giovanni},
  booktitle = {International Conference on Cloud Engineering (IC2E)},
  pages = {165--174},
  year = 2014,
  month = Mar,
  publisher = IEEE,
  address = {Boston, MA, USA},
  abstract = { One of the key enablers of a cloud provider
	competitiveness is ability to over-commit shared
	infrastructure at ratios that are higher than those of other
	competitors, without compromising non-functional requirements,
	such as performance. A widely recognized impediment to
	achieving this goal is so called ``Virtual Machines sprawl'',
	a phenomenon referring to the situation when customers order
	Virtual Machines (VM) on the cloud, use them extensively and
	then leave them inactive for prolonged periods of time. Since
	a typical cloud provisioning system treats new VM provision
	requests according to the nominal virtual hardware
	specification, an often occurring situation is that the
	nominal resources of a cloud/pool become exhausted fast while
	the physical hosts utilization remains low. We present IBM
	adaPtive UtiLiSation AcceleratoR (IBM PULSAR), a cloud
	resources scheduler that extends OpenStack Nova Filter
	Scheduler. IBM PULSAR recognises that effective safely
	attainable over-commit ratio varies with time due to
	workloads' variability and dynamically adapts the effective
	over-commit ratio to these changes.},
}
```

```
@ARTICLE{clusterdata:Zhang2014-Harmony,
  author = {Qi Zhang and Mohamed Faten Zhani and Raouf Boutaba and
	Joseph L Hellerstein},
  title = {Dynamic heterogeneity-aware resource provisioning in the cloud},
  journal = {IEEE Transactions on Cloud Computing (TCC)},
  year = 2014,
  month = Mar,
  volume = 2,
  number = 1,
  abstract = { Data centers consume tremendous amounts of energy in
	terms of power distribution and cooling. Dynamic capacity
	provisioning is a promising approach for reducing energy
	consumption by dynamically adjusting the number of active
	machines to match resource demands. However, despite extensive
	studies of the problem, existing solutions have not fully
	considered the heterogeneity of both workload and machine
	hardware found in production environments. In particular,
	production data centers often comprise heterogeneous machines
	with different capacities and energy consumption
	characteristics. Meanwhile, the production cloud workloads
	typically consist of diverse applications with different
	priorities, performance and resource requirements. Failure to
	consider the heterogeneity of both machines and workloads will
	lead to both sub-optimal energy-savings and long scheduling
	delays, due to incompatibility between workload requirements
	and the resources offered by the provisioned machines. To
	address this limitation, we present Harmony, a
	Heterogeneity-Aware dynamic capacity provisioning scheme for
	cloud data centers. Specifically, we first use the K-means
	clustering algorithm to divide workload into distinct task
	classes with similar characteristics in terms of resource and
	performance requirements. Then we present a technique that
	dynamically adjusting the number of machines to minimize total
	energy consumption and scheduling delay. Simulations using
	traces from a Google's compute cluster demonstrate Harmony can
	reduce energy by 28 percent compared to
	heterogeneity-oblivious solutions.},
}
```

```
@INPROCEEDINGS{clusterdata:Di2013a,
  title = {Optimization of cloud task processing with checkpoint-restart mechanism},
  author = {Di, Sheng and Robert, Yves and Vivien, Fr\'ed\'eric and
	Kondo, Derrick and Wang, Cho-Li and Cappello, Franck},
  booktitle = {25th International Conference on High Performance
	Computing, Networking, Storage and Analysis (SC)},
  year = 2013,
  month = Nov,
  address = {Denver, CO, USA},
  abstract = {In this paper, we aim at optimizing fault-tolerance
	techniques based on a checkpointing/restart mechanism, in the
	context of cloud computing. Our contribution is
	three-fold. (1) We derive a fresh formula to compute the
	optimal number of checkpoints for cloud jobs with varied
	distributions of failure events. Our analysis is not only
	generic with no assumption on failure probability
	distribution, but also attractively simple to apply in
	practice. (2) We design an adaptive algorithm to optimize the
	impact of checkpointing regarding various costs like
	checkpointing/restart overhead. (3) We evaluate our optimized
	solution in a real cluster environment with hundreds of
	virtual machines and Berkeley Lab Checkpoint/Restart
	tool. Task failure events are emulated via a production trace
	produced on a large-scale Google data center. Experiments
	confirm that our solution is fairly suitable for Google
	systems. Our optimized formula outperforms Young's formula by
	3--10 percent, reducing wallclock lengths by 50--100 seconds
	per job on average.},
}
```

```
@inproceedings{clusterdata:Qiang2013-anomaly,
  author = {Qiang Guan and Song Fu},
  title = {Adaptive Anomaly Identification by Exploring Metric
	Subspace in Cloud Computing Infrastructures},
  booktitle = {32nd IEEE Symposium on Reliable Distributed Systems (SRDS)},
  year = 2013,
  month = Sep,
  pages = {205--214},
  address = {Braga, Portugal},
  abstract = { Cloud computing has become increasingly popular by
	obviating the need for users to own and maintain complex
	computing infrastructures. However, due to their inherent
	complexity and large scale, production cloud computing systems
	are prone to various runtime problems caused by hardware and
	software faults and environmental factors. Autonomic anomaly
	detection is a crucial technique for understanding emergent,
	cloud-wide phenomena and self-managing cloud resources for
	system-level dependability assurance. To detect anomalous
	cloud behaviors, we need to monitor the cloud execution and
	collect runtime cloud performance data. These data consist of
	values of performance metrics for different types of failures,
	which display different correlations with the performance
	metrics. In this paper, we present an adaptive anomaly
	identification mechanism that explores the most relevant
	principal components of different failure types in cloud
	computing infrastructures. It integrates the cloud performance
	metric analysis with filtering techniques to achieve
	automated, efficient, and accurate anomaly identification. The
	proposed mechanism adapts itself by recursively learning from
	the newly verified detection results to refine future
	detections. We have implemented a prototype of the anomaly
	identification system and conducted experiments in an
	on-campus cloud computing environment and by using the Google
	data center traces. Our experimental results show that our
	mechanism can achieve more efficient and accurate anomaly
	detection than other existing schemes.},
}
```

```
@ARTICLE{clusterdata:Zhani2013-HARMONY,
  title = {{HARMONY}: dynamic heterogeneity-aware resource provisioning in the cloud},
  author = {Qi Zhang and Mohamed Faten Zhani and Raouf Boutaba and
	Joseph L. Hellerstein},
  journal = {The 33rd International Conference on Distributed Computing Systems (ICDCS)},
  year = 2013,
  pages = {510--519},
  month = Jul,
  address = {Philadelphia, PA, USA},
  abstract = { Data centers today consume tremendous amount of energy
	in terms of power distribution and cooling. Dynamic capacity
	provisioning is a promising approach for reducing energy
	consumption by dynamically adjusting the number of active
	machines to match resource demands. However, despite extensive
	studies of the problem, existing solutions for dynamic
	capacity provisioning have not fully considered the
	heterogeneity of both workload and machine hardware found in
	production environments. In particular, production data
	centers often comprise several generations of machines with
	different capacities, capabilities and energy consumption
	characteristics. Meanwhile, the workloads running in these
	data centers typically consist of a wide variety of
	applications with different priorities, performance objectives
	and resource requirements. Failure to consider heterogenous
	characteristics will lead to both sub-optimal energy-savings
	and long scheduling delays, due to incompatibility between
	workload requirements and the resources offered by the
	provisioned machines. To address this limitation, in this
	paper we present HARMONY, a Heterogeneity-Aware Resource
	Management System for dynamic capacity provisioning in cloud
	computing environments. Specifically, we first use the K-means
	clustering algorithm to divide the workload into distinct task
	classes with similar characteristics in terms of resource and
	performance requirements. Then we present a novel technique
	for dynamically adjusting the number of machines of each type
	to minimize total energy consumption and performance penalty
	in terms of scheduling delay. Through simulations using real
	traces from Google's compute clusters, we found that our
	approach can improve data center energy efficiency by up to
	28\% compared to heterogeneity-oblivious solutions.},
}
```

```
@INPROCEEDINGS{clusterdata:Amoretti2013
  title = {A cooperative approach for distributed task execution in autonomic clouds},
  author = {Amoretti, M. and Lafuente, A.L. and Sebastio, S.},
  booktitle = {21st Euromicro International Conference on Parallel,
	Distributed and Network-Based Processing (PDP)},
  publisher = {IEEE},
  year = 2013,
  month = Feb,
  pages = {274--281},
  abstract = {Virtualization and distributed computing are two key
	pillars that guarantee scalability of applications deployed in
	the Cloud. In Autonomous Cooperative Cloud-based Platforms,
	autonomous computing nodes cooperate to offer a PaaS Cloud for
	the deployment of user applications. Each node must allocate
	the necessary resources for applications to be executed with
	certain QoS guarantees. If the QoS of an application cannot be
	guaranteed a node has mainly two options: to allocate more
	resources (if it is possible) or to rely on the collaboration
	of other nodes. Making a decision is not trivial since it
	involves many factors (e.g. the cost of setting up virtual
	machines, migrating applications, discovering
	collaborators). In this paper we present a model of such
	scenarios and experimental results validating the convenience
	of cooperative strategies over selfish ones, where nodes do
	not help each other. We describe the architecture of the
	platform of autonomous clouds and the main features of the
	model, which has been implemented and evaluated in the DEUS
	discrete-event simulator. From the experimental evaluation,
	based on workload data from the Google Cloud Backend, we can
	conclude that (modulo our assumptions and simplifications) the
	performance of a volunteer cloud can be compared to that of a
	Google Cluster.},
  doi = {10.1109/PDP.2013.47},
  ISSN = {1066-6192},
  address = {Belfast, UK},
  url = {http://doi.ieeecomputersociety.org/10.1109/PDP.2013.47},
}
```

```
@INPROCEEDINGS{clusterdata:Di2012b,
  title = {Host load prediction in a {Google} compute cloud with a {Bayesian} model},
  author = {Di, Sheng and Kondo, Derrick and Cirne, Walfredo},
  booktitle = {International Conference on High Performance Computing,
	Networking, Storage and Analysis (SC)},
  year = 2012,
  month = Nov,
  isbn = {978-1-4673-0804-5},
  address = {Salt Lake City, UT, USA},
  pages = {21:1--21:11},
  abstract = {Prediction of host load in Cloud systems is critical for
	achieving service-level agreements. However, accurate
	prediction of host load in Clouds is extremely challenging
	because it fluctuates drastically at small timescales. We
	design a prediction method based on Bayes model to predict the
	mean load over a long-term time interval, as well as the mean
	load in consecutive future time intervals. We identify novel
	predictive features of host load that capture the expectation,
	predictability, trends and patterns of host load. We also
	determine the most effective combinations of these features
	for prediction. We evaluate our method using a detailed
	one-month trace of a Google data center with thousands of
	machines. Experiments show that the Bayes method achieves high
	accuracy with a mean squared error of 0.0014. Moreover, the
	Bayes method improves the load prediction accuracy by
	5.6--50\% compared to other state-of-the-art methods based on
	moving averages, auto-regression, and/or noise filters.},
  url = {http://dl.acm.org/citation.cfm?id=2388996.2389025},
  publisher = {IEEE Computer Society Press},
}
```

```
@INPROCEEDINGS{clusterdata:Zhang2012,
  title = {Dynamic energy-aware capacity provisioning for cloud computing environments},
  author = {Zhang, Qi and Zhani, Mohamed Faten and Zhang, Shuo and
	Zhu, Quanyan and Boutaba, Raouf and Hellerstein, Joseph L.},
  booktitle = {9th ACM International Conference on Autonomic Computing (ICAC)},
  year = 2012,
  month = Sep,
  isbn = {978-1-4503-1520-3},
  address = {San Jose, CA, USA},
  pages = {145--154},
  acmid = {2371562},
  publisher = {ACM},
  doi = {10.1145/2371536.2371562},
  keywords = {cloud computing, energy management, model predictive
	control, resource management},
  abstract = {Data centers have recently gained significant popularity
	as a cost-effective platform for hosting large-scale service
	applications. While large data centers enjoy economies of
	scale by amortizing initial capital investment over large
	number of machines, they also incur tremendous energy cost in
	terms of power distribution and cooling. An effective approach
	for saving energy in data centers is to adjust dynamically the
	data center capacity by turning off unused machines. However,
	this dynamic capacity provisioning problem is known to be
	challenging as it requires a careful understanding of the
	resource demand characteristics as well as considerations to
	various cost factors, including task scheduling delay, machine
	reconfiguration cost and electricity price fluctuation.  In
	this paper, we provide a control-theoretic solution to the
	dynamic capacity provisioning problem that minimizes the total
	energy cost while meeting the performance objective in terms
	of task scheduling delay. Specifically, we model this problem
	as a constrained discrete-time optimal control problem, and
	use Model Predictive Control (MPC) to find the optimal control
	policy. Through extensive analysis and simulation using real
	workload traces from Google's compute clusters, we show that
	our proposed framework can achieve significant reduction in
	energy cost, while maintaining an acceptable average
	scheduling delay for individual tasks.},
}
```

```
@INPROCEEDINGS{clusterdata:Ali-Eldin2012
  title = {Efficient provisioning of bursty scientific workloads on the
	cloud using adaptive elasticity control},
  author = {Ahmed Ali-Eldin and Maria Kihl and Johan Tordsson and Erik Elmroth},
  booktitle = {3rd Workshop on Scientific Cloud Computing (ScienceCloud)},
  year = 2012,
  month = Jun,
  address = {Delft, The Nederlands},
  isbn = {978-1-4503-1340-7},
  pages = {31--40},
  url = {http://dl.acm.org/citation.cfm?id=2287044},
  doi = {10.1145/2287036.2287044},
  publisher = {ACM},
  abstract = {Elasticity is the ability of a cloud infrastructure to
	dynamically change the amount of resources allocated to a
	running service as load changes. We build an autonomous
	elasticity controller that changes the number of virtual
	machines allocated to a service based on both monitored load
	changes and predictions of future load. The cloud
	infrastructure is modeled as a G/G/N queue. This model is used
	to construct a hybrid reactive-adaptive controller that
	quickly reacts to sudden load changes, prevents premature
	release of resources, takes into account the heterogeneity of
	the workload, and avoids oscillations. Using simulations with
	Web and cluster workload traces, we show that our proposed
	controller lowers the number of delayed requests by a factor
	of 70 for the Web traces and 3 for the cluster traces when
	compared to a reactive controller. Our controller also
	decreases the average number of queued requests by a factor of
	3 for both traces, and reduces oscillations by a factor of 7
	for the Web traces and 3 for the cluster traces. This comes at
	the expense of between 20\% and 30\% over-provisioning, as
	compared to a few percent for the reactive controller.},
}
```

```
@INPROCEEDINGS{clusterdata:Sharma2011,
  title = {Modeling and synthesizing task placement constraints in
	{Google} compute clusters},
  author = {Sharma, Bikash and Chudnovsky, Victor and Hellerstein,
	Joseph L. and Rifaat, Rasekh and Das, Chita R.},
  booktitle = {2nd ACM Symposium on Cloud Computing (SoCC)},
  year = 2011,
  month = Oct,
  isbn = {978-1-4503-0976-9},
  address = {Cascais, Portugal},
  pages = {3:1--3:14},
  url = {http://doi.acm.org/10.1145/2038916.2038919},
  doi = {10.1145/2038916.2038919},
  publisher = {ACM},
  keywords = {benchmarking, benchmarks, metrics, modeling, performance
	evaluation, workload characterization},
  abstract = {Evaluating the performance of large compute clusters
	requires benchmarks with representative workloads. At Google,
	performance benchmarks are used to obtain performance metrics
	such as task scheduling delays and machine resource
	utilizations to assess changes in application codes, machine
	configurations, and scheduling algorithms. Existing approaches
	to workload characterization for high performance computing
	and grids focus on task resource requirements for CPU, memory,
	disk, I/O, network, etc. Such resource requirements address
	how much resource is consumed by a task. However, in addition
	to resource requirements, Google workloads commonly include
	task placement constraints that determine which machine
	resources are consumed by tasks. Task placement constraints
	arise because of task dependencies such as those related to
	hardware architecture and kernel version.  

	This paper develops
	methodologies for incorporating task placement constraints and
	machine properties into performance benchmarks of large
	compute clusters. Our studies of Google compute clusters show
	that constraints increase average task scheduling delays by a
	factor of 2 to 6, which often results in tens of minutes of
	additional task wait time. To understand why, we extend the
	concept of resource utilization to include constraints by
	introducing a new metric, the Utilization Multiplier (UM). UM
	is the ratio of the resource utilization seen by tasks with a
	constraint to the average utilization of the resource. UM
	provides a simple model of the performance impact of
	constraints in that task scheduling delays increase with
	UM. Last, we describe how to synthesize representative task
	constraints and machine properties, and how to incorporate
	this synthesis into existing performance benchmarks. Using
	synthetic task constraints and machine properties generated by
	our methodology, we accurately reproduce performance metrics
	for benchmarks of Google compute clusters with a discrepancy
	of only 13\% in task scheduling delay and 5\% in resource
	utilization.},
}
```

```
@INPROCEEDINGS{clusterdata:Wang2011,
  title = {Towards synthesizing realistic workload traces for studying
	the {Hadoop} ecosystem},
  author = {Wang, Guanying and Butt, Ali R. and Monti, Henry and Gupta, Karan},
  booktitle = {19th IEEE Annual International Symposium on Modelling,
	Analysis, and Simulation of Computer and Telecommunication
	Systems (MASCOTS)},
  year = 2011,
  month = Jul,
  isbn = {978-0-7695-4430-4},
  pages = {400--408},
  url = {http://people.cs.vt.edu/~butta/docs/mascots11-hadooptrace.pdf},
  doi = {10.1109/MASCOTS.2011.59},
  publisher = {IEEE Computer Society},
  address = {Raffles Hotel, Singapore},
  keywords = {Cloud computing, Performance analysis, Design
	optimization, Software performance modeling},
  abstract = {Designing cloud computing setups is a challenging
	task. It involves understanding the impact of a plethora of
	parameters ranging from cluster configuration, partitioning,
	networking characteristics, and the targeted applications'
	behavior. The design space, and the scale of the clusters,
	make it cumbersome and error-prone to test different cluster
	configurations using real setups. Thus, the community is
	increasingly relying on simulations and models of cloud setups
	to infer system behavior and the impact of design choices. The
	accuracy of the results from such approaches depends on the
	accuracy and realistic nature of the workload traces
	employed. Unfortunately, few cloud workload traces are
	available (in the public domain). In this paper, we present
	the key steps towards analyzing the traces that have been made
	public, e.g., from Google, and inferring lessons that can be
	used to design realistic cloud workloads as well as enable
	thorough quantitative studies of Hadoop design. Moreover, we
	leverage the lessons learned from the traces to undertake two
	case studies: (i) Evaluating Hadoop job schedulers, and (ii)
	Quantifying the impact of shared storage on Hadoop system
	performance.}
}
```