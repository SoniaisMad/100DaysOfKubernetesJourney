# Jobs and Cron Jobs

A Job creates one or more Pods to perform a given task (that takes some time -> batch, backup, cleaning, migration...)  
The Job object takes the responsibility of Pod failures. It makes sure that the given task is completed successfully. Once the task is complete, all the Pods have terminated automatically. Job configuration options include:

parallelism - to set the number of pods allowed to run in parallel;
completions - to set the number of expected completions;
activeDeadlineSeconds - to set the duration of the Job;
backoffLimit - to set the number of retries before Job is marked as failed;
ttlSecondsAfterFinished - to delay the clean up of the finished Jobs.
Starting with the Kubernetes 1.4 release, we can also perform Jobs at scheduled times/dates with CronJobs, where a new Job object is created about once per each execution cycle. The CronJob configuration options include:

startingDeadlineSeconds - to set the deadline to start a Job if scheduled time was missed;
concurrencyPolicy - to allow or forbid concurrent Jobs or to replace old Jobs with new ones. 

Aurelie Vache videos : youtube.com/watch?v=UMJg_JasNXw, https://www.youtube.com/watch?v=X5Lx757zeWM
