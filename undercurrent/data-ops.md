#   Data ops
    DataOps is a collection of technical practices, workflows, cultural norms, and architectural patterns that enable:
    
    Rapid innovation and experimentation delivering new insights to customers with increasing velocity
    Extremely high data quality and very low error rates
    Collaboration across complex arrays of people, technology, and environments


#   Automation

    Engineers will gradually migrate their cron jobs to Airflow jobs.
    Now, dependencies are checked before jobs run.
    More jobs can be packed into a given time because each job can start as soon as upstream data is ready rather than 
    at a fixed, predetermined time.

    The data engineering team still has room for operational improvements. 
    For instance, eventually, a data scientist deploys a broken DAG, bringing down the Airflow webserver and leaving the data team operationally blind.
    After enough such headaches, the data engineering team realizes that they need to stop allowing manual DAG deployments. In their next phase of operational maturity, they adopt automated DAG deployment.
    
    DAGs are tested before deployment, and monitoring processes ensure that the new DAGs start running properly.
    In addition, data engineers block the deployment of new Python dependencies until installation is validated.
    After automation is adopted, the data team is much happier and experiences far fewer headaches.

#   Obervability and monitoring

    As we tell our clients, “data is a silent killer”. We’ve seen countless examples of bad data lingering in reports for months or years. Executives may make key decisions from this bad data, only to discover a substantial time later that the data was wrong. The outcomes are usually bad, and sometimes catastrophic for the business. Initiatives are undermined and destroyed, years of work wasted. In some of the worst cases, companies may be led to financial or technical disaster by bad data.

    Another horror story is when the systems that create the data for reports randomly stop working, resulting in reports being delayed by several days. The data team doesn’t know until they're asked by stakeholders why reports are late or producing stale information. Eventually, different stakeholders lose trust in the capabilities of the data system and start their quasi-data team. The result is a ton of different unstable systems, reports, and silos.

    If you're not observing and monitoring your data, and the systems that produce the data, you’re inevitably going to experience your own data horror story. Observability, monitoring, logging, alerting, tracing are all critical to getting ahead of any problems that will occur along the data engineering lifecycle. We recommend you incorporate statistical process control (SPC) to understand whether events being monitored are out of line, and which incidents are worth responding to.

    We’ll cover many aspects of monitoring and observability throughout the data engineering lifecycle in later chapters.

    

#   Incident response

    A high-functioning data team using DataOps will be able to quickly ship new data products. But mistakes will inevitably happen. A system may have downtime, a new data model may break downstream reports, a machine learning model may become stale and provide bad predictions, and countless other things may happen that interrupt the data engineering lifecycle. Incident response is about using the automation and observability capabilities mentioned above to rapidly identify root causes of an incident, and resolve the incident as reliably and quickly as possible.

    Incident response isn’t just about technology and tools, though they are immensely useful. It’s also about open and blameless communication, both on the data engineering team, and across the organization. As Werner Vogels is famous for saying, “Everything breaks all the time.” Data engineers must be prepared for disaster, and ready to respond as swiftly and efficiently as possible. Even better, data engineers should proactively find issues before the business reports them. Trust takes a long time to build and can be lost in minutes. In the end, incident response is as much about retroactively responding to incidents as proactively addressing them before they happen.

