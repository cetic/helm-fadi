Changelog
=====

This branch adds Apache Pulsar to the stack.

Integration with Nifi can be done with https://github.com/streamlio/nifi-pulsar-bundle.

Usage 
----
Get the [Pulsar helm chart](https://github.com/apache/pulsar/tree/master/deployment/kubernetes/helm/pulsar):

```
mkdir -p dependency_chart/pulsar
git clone git@github.com:apache/pulsar.git /tmp/pulsar
cp -rpi /tmp/pulsar/deployment/kubernetes/helm/pulsar/* ./dependency_chart/pulsar/  
helm dependency update
rm -rf /tmp/pulsar
```

TODO:

* add documentation on default config settings and usage
* empty template/Notes.txt for it to work because it does not play well with dependency_chart, needs to be reenabled with an additional section for Pulsar.