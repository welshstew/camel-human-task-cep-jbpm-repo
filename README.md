jBPM Project with Complex Event Processing and Human Task
=====================================
This is a [JBoss BPM Suite](http://www.jboss.org/products/bpmsuite/overview/) project with a business process that is supposed to be triggered from [JBoss Fuse](http://www.jboss.org/products/fuse/overview/). It shows how Camel errors are handled and passed to BPMS for Complex Event Processing and Human Task creation using [camel-jbpm](http://camel.apache.org/jbpm.html) connector.
You can read a more detailed blog post with instructions about this demo [here](http://www.ofbizian.com/)


####Process Flow
The process evaluates each error coming from Fuse using CEP and if there are more than 5 errors in 10 seconds, it marks the error as critical and creates Human Tasks for someone review the error. If the error doesn't qualify as a critical one, then it is logged and no Human Task is created. Here is the BMN2 diagram:

![BMN2 Diagram](http://2.bp.blogspot.com/-e6gZAjJmUmE/Vc-SFPMRneI/AAAAAAAACko/WTKqyQZvG9E/s1600/project1.camel.demo%25281%2529.png)


####Running the Demo with JBoss Fuse 6.2 and JBoss BPMS

- **From JBoss BPM System deploy the process:**
Authoring -> Administration, Repositories -> Clone repository and clone thus project.
Authoring -> Project authoring, Open Project Editor, Build and Deploy

- **Run Fuse and deploy the Camel Route:**
Clone https://github.com/bibryam/camel-jbpm-demo.git and deploy the Camel route to Fuse by following the instructions.
The Camel route will quickly send 10 errors and the business process will create processes for each of them and qualify only one as critical error with a Human Task associated. The Human Tasks and the processes contains full details about the errors.

 
####License
ASLv2

