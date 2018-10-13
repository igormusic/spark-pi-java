# spark-pi-java
Sample Spring Boot Java project using Oshinko Spark Cluster.

*OSX instructions*

Install minishift:
```
$ brew cask install minishift
```

Install OpenShift CLI:
```
$ brew install openshift-cli
```

Create Spark Cluster:
```
$ oc new-project spark-cluster
```

Get Oshinko OpenShift templates:
```
$ oc create -f https://radanalytics.io/resources.yaml
```

Start Oshinko Web-UI
```
$ oc new-app oshinko-webui
```

Get route for oshink-webui:

```
$ oc get route oshinko-web
```

To build and run application:
```
oc new-app --template oshinko-java-spark-build-dc \
    -p APPLICATION_NAME=sparkpi \
    -p GIT_URI=https://github.com/igormusic/spark-pi-java \
    -p APP_FILE=SparkPiBoot-0.0.1-SNAPSHOT.jar
```
