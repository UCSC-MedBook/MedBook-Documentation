A place to store the different interesting and useful links that get passed around among the MedBook team,
or any other documents that folks find and want to keep for future reference.

### Library References
* [q API reference](https://github.com/kriskowal/q/wiki/API-Reference)

### Meteor Guides
* [promise anti-patterns](http://taoofcode.net/promise-anti-patterns/)
* The METEOR_OFFLINE_CATALOG prevents meteor from checking the package server. This is very useful when you are on the airplane.
So to use it, set it your shell like this: `export METEOR_OFFLINE_CATALOG=1` before you start your meteor app.\
* [frequently used mongoDB field names should be short](http://objectrocket.com/blog/how-to/short-field-names-mongodb)
* [what relational DB folks think about web stores](http://www.mongodb-is-web-scale.com/)

### Git 
* [OneFlow](http://endoflineblog.com/oneflow-a-git-branching-model-and-workflow) an evolution of GitFlow to consider using

### Jupyter / IPython
* [Why Jupyter? Its grant application](https://blog.jupyter.org/2015/07/07/project-jupyter-computational-narratives-as-the-engine-of-collaborative-data-science/) - " the core problem we are trying to solve is the 
collaborative creation of reproducible computational narratives"
* [Example Zika analysis notebook](http://nbviewer.jupyter.org/github/maayanlab/Zika-RNAseq-Pipeline/blob/master/Zika.ipynb)
* [Rob's MedBook notebook](https://github.com/rcurrie/treehouse/blob/master/Outlier.ipynb)
* [What python/R packages are in the docker we’re using:](https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook) 
* [* Multi-tiered genomic analysis of head and neck cancer ties TP53 mutation to 3p loss, by A. Gross et al. (Nature Genetics 2014).](https://github.com/theandygross/TCGA/tree/master/Analysis_Notebooks#guide-to-running) 
* [Pretty pictures exploring TP53:](https://github.com/theandygross/TCGA/blob/master/Analysis_Notebooks/TP53_exploration.ipynb) 
* [* Gallery of interesting notebooks](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks) 
* [* GA4GH Examples accessing variants, expression etc... (under notebooks):](https://github.com/BD2KGenomics/bioapi-examples) 
* [* Munging 1TB of data using Spark in Jupyter](http://blog.insightdatalabs.com/jupyter-on-apache-spark-step-by-step/) 
* [The good and bad of HDF5](http://cyrille.rossant.net/moving-away-hdf5/)
* [The State of Jupyter - O'Reilly](https://www.oreilly.com/ideas/the-state-of-jupyter)
* [Google Cloud Platform - Jupyter + SQL](https://cloud.google.com/datalab/)
* [Maarten Breddels | A billion stars in the Jupyter Notebook](https://youtu.be/bP-JBbjwLM8) [video] Check out the interactive widgets mid way through to end
* [Reproducible Data Analysis in Jupyter](http://jakevdp.github.io/blog/2017/03/03/reproducible-data-analysis-in-jupyter/) [video] Guide for jupyter-> python package + unit tests
* [interactive tables in jupyter notebook](http://nbviewer.jupyter.org/gist/TimShawver/8fcef51dd3c222ed25306c002ab89b60) Pulls data frame into a javascript variable
* [Extension that provides search as well as turning notebooks into modules](https://github.com/jupyter-incubator/contentmanagement) see also the [Whoosh full-text search](https://pypi.python.org/pypi/Whoosh/)
* [Binder workshop](http://ivory.idyll.org/blog/2017-binder-workshop.html) / [papermill - "Choose a notebook to run based on outcome of a previous notebook"](https://github.com/nteract/papermill)

### Flask
* [a broad run down of some of the elements of the restful tooling](http://michal.karzynski.pl/blog/2016/06/19/building-beautiful-restful-apis-using-flask-swagger-ui-flask-restplus/)
* [Swagger syntactic sugar](https://github.com/ga4gh/cgtd/blob/master/cgtd/cgtd.py#L120)
* [automatic api documentation with swagger!](http://ucsf.edu.cancergenetrust.org/api)

### Cancer
* [Oncotree](http://oncotree.mskcc.org/oncotree/) A tree visualization of cancer types. Some nice json under the hood.
* [Fighting Cancer Through Curiosity](http://stevenkeating.info/main.html) ([Youtube](https://www.youtube.com/watch?v=U5SafKJgqPM)) - TED talk on data sharing by a cancer patient
* [Forbes: Dana Farber study on precision medicine + brain cancer ](http://www.forbes.com/sites/arleneweintraub/2017/01/19/how-precision-medicine-could-be-a-lifesaver-for-kids-with-brain-cancer)
* [the NMTRC’s genomic-based treatment for childhood cancer](https://beatnb.org/blog/2015/12/18/how-were-beating-kids-cancer-with-computers/)
* [SU2C's Phil Sharp + St. Baldrick’s Pediatric Dream Team's Dr. Crystal Mackall wrap up the Summit (Jan 2017)](https://www.facebook.com/su2c/videos/10153996991430876/)
* [Cognoma](https://github.com/cognoma/cognoma) - machine learning cancer webapp with sample/genes api. [API](https://github.com/cognoma/core-service/blob/master/doc/api.md)
* [OMOP clinical data schema](http://harvest.research.chop.edu/demos/) - used by PMI and CHOP. [postgres webapp](https://github.com/OHDSI/Atlas)

### Bioinformatics
* [GDC data model](https://gdc.nci.nih.gov/developers/gdc-data-model/gdc-data-model-components)
* [example patient view in cbioportal](http://www.cbioportal.org/case.do?cancer_study_id=lgg_ucsf_2014&case_id=P04)
* [Airflow for a DAG workflow](https://danidelvalle.me/2016/09/12/im-sorry-cron-ive-met-airbnbs-airflow/)
* [RNA-Seq in Mice w/Limma](https://f1000research.com/articles/5-1408/v2#ref-24) Also of interest due to presentation - embedded R code - uses Knitr.
* [R's GA4GH Library + API example](https://github.com/labbcb/GA4GHclient/issues/23#issuecomment-271931574)
* [Python GA4GH Library examples](https://github.com/BD2KGenomics/bioapi-examples/tree/master/python_notebooks)
* [Standards and guidelines for the interpretation of sequence variants](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4544753/)
* [Nature - broad-spectrum RNA-seq analysis](https://www.nature.com/articles/s41467-017-00050-4) and associated [pipeline in Docker](https://bioinform.github.io/rnacocktail/)


### Machine Learning
* [Distill - machine learning interactive viz journal](http://distill.pub/about/)

### General Programming
* [programmer interrupted](http://blog.ninlabs.com/2013/01/programmer-interrupted/) effect of disruptions while coding
* [On being a senior engineer](http://www.kitchensoap.com/2012/10/25/on-being-a-senior-engineer/) critical non-coding skills
* [Headless Mode coming to Chrome](https://www.chromestatus.com/features/5678767817097216)

### Data Sharing
* [Nature - Empty rhetoric over data sharing slows science
](http://www.nature.com/news/empty-rhetoric-over-data-sharing-slows-science-1.22133)
