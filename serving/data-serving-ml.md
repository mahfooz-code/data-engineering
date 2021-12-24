#   Machine learning
    Machine learning is one of the most exciting technology revolutions of our time. Once organizations reach a high level of data maturity, they can begin to identify problems that are amenable to machine learning and start organizing a machine learning practice.

The responsibilities of data engineers overlap significantly in analytics and machine learning, and the boundaries between data engineering, machine learning engineering, and analytics engineering can be fuzzy. For example, a data engineer may need to support Apache Spark clusters that facilitate both analytics pipelines and machine learning model training. They may also need to provide a Prefect or Dagster system that orchestrates tasks across teams, and support metadata and cataloging systems that track data history and lineage. Setting these domains of responsibility, and the relevant reporting structures, is a critical organizational decision.

One recently developed tool that combines data engineering and ML engineering is the feature store (e.g. FEAST and Tecton, among others). Feature stores are designed to reduce the operational burden for machine learning engineers, by maintaining feature history and versions, supporting feature sharing between teams, and providing basic operational and orchestration capabilities, such as backfilling. In practice, data engineers are part of the core support team for feature stores to support ML engineering.

Should a data engineer be familiar with machine learning? It certainly helps. Regardless of the operational boundary between data engineering, ML engineering, and business analytics, etc., data engineers should maintain operational knowledge about the teams they work with. A good data engineer is conversant in the fundamental machine learning techniques and related data processing requirements (deep learning, featurization, etc.), in the use cases for models within their company, and the responsibilities of the organization’s various analytics teams. This helps to maintain efficient communication and facilitate collaboration. Ideally, data engineers will build tools in collaboration with other teams that neither team is capable of building on its own.

This book cannot possibly cover machine learning in-depth. There’s a growing ecosystem of books, videos, articles, and communities if you’re interested in learning more; we include a few additional references in the further reading section at the end of this chapter.

Below are some considerations for the Serving Data phase, specific to machine learning:

Is the data of sufficient quality to perform reliable feature engineering? Quality requirements and assessments are developed in close collaboration with teams consuming the data.

Is the data discoverable? Can data scientists and machine learning engineers easily find useful data?

Where are the technical and organizational boundaries between data engineering and machine learning engineering? This organizational question has major architectural implications.

The dataset properly represents ground truth and isn’t unfairly biased.

While machine learning is exciting, our experience is that companies often prematurely dive into it. Before investing a ton of resources into machine learning, take the time to build a solid data foundation. This means setting up the best systems and architecture across the data engineering lifecycle, as well as the machine learning lifecycle. More often than not, get good with analytics before moving to machine learning. Many companies have seen their machine learning dreams dashed because they undertook initiatives without appropriate foundations in place. On the other hand, data engineers should keep the serving stage of the data engineering lifecycle in mind at all times as they’re building out the other stages, both as motivation and to steer and shape their architectures and initiatives.