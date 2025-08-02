
Key Points:

completions: 1
* Job will run until one successful Pod completion.
* If the Pod fails, it will retry (based on backoff limits).

parallelism: 1
* Only one Pod runs at a time.
* If you set it to 3, three Pods would run simultaneously in parallel.

restartPolicy: Never
* Once the Pod completes or fails, it won’t restart.

BusyBox:

* BusyBox is a lightweight Linux utility image often called "the Swiss Army Knife of Linux".
* It provides a minimal set of Unix/Linux command-line tools (like sh, ls, echo, cat, etc.) in a single executable.
* Commonly used in testing, debugging, and simple scripting tasks in Kubernetes because it is very small (~1MB).



 Create the Job
 
$kubectl apply -f job.yml

Check Job status
$ kubectl get jobs -n my-app

View Pods created by the Job
$ kubectl get pods -n my-app

Check logs of the Pod (output of echo Hello World)
$ kubectl logs <pod-name> -n my-app

Delete the Job
$ kubectl delete job demo-job -n my-app
