# SparkUI

Spark has become the standard for most of the data science analysis. It can be used as an ETL platform where tasks are connected with data being stored in some kind of distributed file system. The spark nodes can access those datasets directly from the filesystems.

Luigi is a workflow model which can be used to build a pipeline. Each of the tasks in a pipeline can be scheduled via Luigi and all the dependencies can be managed via Luigi framework. 

This project plans to build a user interface which integrates Luigi and Spark interfaced via a graph based database. We plan to explore NEO4J and GraphX to evaluate the effectiveness of building DAG. This could also be done via JS framework but it is outside the scope of this project. The UI produced by NEO4J will be used to build a LUIGI based framework and all the requirements for a LUIGI task would be generated via this UI. 

The code generation will happen via JINJA and will use the same model as is done for building cookecutter code.The would take away the requirement for the developer to know the inner details of Luigi and the developer can focus only on the SPARK tasks. The idea is that the userinterface will be use a graph based model - either SPARK graphx or NEO4J to define the DAG. Once the DAG has been defined, that DAG would be the basis to define the requirements.

All the tasks could be potentially SPARK, Hadoop or simple python based on the requirement and the data size. 

An API would be created to let the framework to know if the task is complete. Any errors within the tasks would be handled by Luigi.All the independent tasks can operate in parallel. This will be different from SPARK based scripts which when create would be sequential.
