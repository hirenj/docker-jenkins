# Docker container for running automated builds locally

We would like to automatically run jobs, and it would be nice to be able to trigger
the jobs using a git repo, or running a build job periodically.

We don't really know what our final job running infrastructure will look like,
so lets just package up jobs into docker containers, and then use Jenkins
to run the jobs periodically.

```
docker run -d -v /var/run/docker.sock:/var/run/docker.sock -v $JENKINS_HOME:/var/jenkins_home -p 8080:8080 hirenj/docker-jenkins
```