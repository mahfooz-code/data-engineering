#   Orchestration
    
    Orchestration is the process of coordinating many jobs to run as quickly and efficiently as possible on a scheduled cadence.
    
    People often mistakenly refer to orchestration tools, like Apache Airflow, as schedulers.
    
    This isn't quite accurate, and there are key differences.
    
    A pure scheduler, such as cron, is aware only of time. 
    
    An orchestration engine, on the other hand, builds in metadata on job dependencies, generally in the form of a DAG (directed acyclic graph).
    
    The DAG can be run once, or be scheduled to run at a fixed interval of daily, weekly, every hour, every five minutes, etc.

    An orchestration system stays online with high availability.
    This allows the orchestration system to sense and monitor constantly without human intervention, and to run new jobs any time they are deployed.
    
    An orchestration system monitors jobs that it manages and kicks off new tasks as internal DAG dependencies are completed.
    It can also monitor external systems and tools to watch for data to arrive and criteria to be met. When certain conditions go out of bounds, the system also sets error conditions and sends alerts through email or other channels. Commonly, you might set an expected completion time for overnight daily data pipelines, perhaps 10 am. If jobs are not done by this time, alerts go out to data engineers and data consumers.

    Orchestration systems typically also build in job history capabilities, visualization, and alerting. 
    
    Apache Oozie was extremely popular in the 2010s, but it was designed to work within a Hadoop cluster and was difficult to use in a more heterogeneous environment.
    Facebook developed Data Swarm for internal use in the late 2000s; this inspired popular tools such as Airflow, which Airbnb open-sourced in 2014.

#   Apache airflow

#   Data swarm

#   Apache oozie

#   Luigi

#   Conductor

#   Prefect

#   Dagster

#   Metaflow



