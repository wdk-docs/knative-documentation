---
title: "Knative Eventing sources"
linkTitle: "Eventing sources"
weight: 30
type: "docs"
---

<!--
This is a generated file and should not be changed manually. All changes should follow the
procedure:

1. Update the information in [`sources.yaml`](./sources.yaml).

2. Run the generator tool:
    ```shell
    go run eventing/sources/generator/main.go
    ```
-->

Event Sources are Kubernetes Custom Resources which provide a mechanism for registering interest in
a class of events from a particular software system. Since different event sources may be described
by different Custom Resources, this page provides an index of the available source resource types as
well as links to installation instructions.

This is a non-exhaustive list of Event sources for Knative.


### Inclusion in this list is not an endorsement, nor does it imply any level of support.


## Sources

These are sources that are installed as `CRD`s.

Name | Status | Support | Description
--- | --- | --- | ---
[AWS SQS](https://github.com/knative/eventing-contrib/blob/master/awssqs/pkg/apis/sources/v1alpha1/aws_sqs_types.go) | Proof of Concept | None | Brings [AWS Simple Queue Service](https://aws.amazon.com/sqs/) messages into Knative.
[Apache Camel](https://github.com/knative/eventing-contrib/blob/master/camel/source/pkg/apis/sources/v1alpha1/camelsource_types.go) | Proof of Concept | None | Allows to use [Apache Camel](https://github.com/apache/camel) components for pushing events into Knative.
[Apache CouchDB](https://github.com/knative/eventing-contrib/tree/{{< branch >}}/couchdb) | Active Development | None | Brings [Apache CouchDB](https://couchdb.apache.org/) messages into Knative.
[Apache Kafka](https://github.com/knative/eventing-contrib/blob/master/kafka/source/pkg/apis/sources/v1alpha1/kafka_types.go) | Proof of Concept | None | Brings [Apache Kafka](https://kafka.apache.org/) messages into Knative.
[BitBucket](https://github.com/nachocano/bitbucket-source) | Proof of Concept | None | Registers for events of the specified types on the specified BitBucket organization/repository. Brings those events into Knative.
[CloudAuditLogsSource](https://github.com/google/knative-gcp/blob/master/docs/examples/cloudauditlogssource/README.md) | Active Development | None | Registers for events of the specified types on the specified [Google Cloud Audit Logs](https://cloud.google.com/logging/docs/audit/). Brings those events into Knative.
[CloudPubSubSource](https://github.com/google/knative-gcp/blob/master/docs/examples/cloudpubsubsource/README.md) | Active Development | None | Brings [Cloud Pub/Sub](https://cloud.google.com/pubsub/) messages into Knative.
[CloudSchedulerSource](https://github.com/google/knative-gcp/blob/master/docs/examples/cloudschedulersource/README.md) | Active Development | None | Create, update, and delete [Google Cloud Scheduler](https://cloud.google.com/scheduler/) Jobs. When those jobs are triggered, receive the event inside Knative.
[CloudStorageSource](https://github.com/google/knative-gcp/blob/master/docs/examples/cloudstoragesource/README.md) | Active Development | None | Registers for events of the specified types on the specified [Google Cloud Storage](https://cloud.google.com/storage/) bucket and optional object prefix. Brings those events into Knative.
[Cron Job](https://knative.dev/docs/eventing/migration/ping) | Replaced by PingSource | None | Deprecated, replace with [PingSource](https://knative.dev/docs/eventing/migration/ping) or a [CronJob using SinkBinding](https://knative.dev/docs/eventing/samples/sinkbinding/)
[GitHub](https://github.com/knative/eventing-contrib/blob/master/github/pkg/apis/sources/v1alpha1/githubsource_types.go) | Proof of Concept | None | Registers for events of the specified types on the specified GitHub organization/repository. Brings those events into Knative.
[GitLab](https://gitlab.com/triggermesh/gitlabsource) | Proof of Concept | None | Registers for events of the specified types on the specified GitLab repository. Brings those events into Knative.
[Kubernetes](https://github.com/knative/eventing/blob/master/pkg/apis/sources/v1alpha1/apiserver_types.go) | Active Development | Knative | Brings Kubernetes API server events into Knative.
[Ping](https://github.com/knative/eventing/blob/master/pkg/apis/sources/v1alpha2/ping_types.go) | In development | None | Uses an in-memory timer to produce events with a fixed payload on a specified cron schedule.



## Meta Sources

These are not directly usable, but make writing a Source much easier.

Name | Status | Support | Description
--- | --- | --- | ---
[Auto Container Source](https://github.com/Harwayne/auto-container-source) | Proof of Concept | None | AutoContainerSource is a controller that allows the Source CRDs _without_ needing a controller. It notices CRDs with a specific label and starts controlling resources of that type. It utilizes Container Source as underlying infrastructure.
[Container Source](https://knative.dev/docs/eventing/migration/sinkbinding) | Deprecated, replaced by SinkBinding | Knative | ContainerSource was an earlier version of SinkBinding which controlled the lifetime of a single Pod which acted as an event source. SinkBinding is more flexible and is preferred.
[Kubebuilder Sample Source](https://github.com/grantr/sample-source) | Proof of Concept | None | Kubebuilder SampleSource is a kubebuilder based implementation supporting the [Writing an Event Source the Hard Way tutorial](../samples/writing-a-source).
[Sample Source](https://github.com/knative/sample-source) | Active Development | Knative | Used as reference implementation supporting [Writing an Event Source from Scratch tutorial](../samples/writing-receive-adapter-source).
[SinkBinding](https://knative.dev/docs/eventing/samples/sinkbinding/) | Active Development | Knative | SinkBinding provides a framework for injecting `K_SINK` (destination address) and `K_CE_OVERRIDES` (JSON cloudevents attributes) environment variables into any Kubernetes resource which has a `spec.template` that looks like a Pod (aka PodSpeccable).



### ContainerSource Containers

These are containers intended to be used with `ContainerSource`.

Name | Status | Support | Description
--- | --- | --- | ---
[AWS CodeCommit](https://github.com/triggermesh/knative-lambda-sources/tree/master/awscodecommit) | Active Development | TriggerMesh | Registers for events of the specified types on the specified AWS CodeCommit repository. Brings those events into Knative.
[AWS Cognito](https://github.com/triggermesh/knative-lambda-sources/tree/master/awscognito) | Active Development | TriggerMesh | Registers for AWS Cognito events. Brings those events into Knative.
[AWS DynamoDB](https://github.com/triggermesh/knative-lambda-sources/tree/master/awsdynamodb) | Active Development | TriggerMesh | Registers for events of on the specified AWS DynamoDB table. Brings those events into Knative.
[AWS Kinesis](https://github.com/triggermesh/knative-lambda-sources/tree/master/awskinesis) | Active Development | TriggerMesh | Registers for events on the specified AWS Kinesis stream. Brings those events into Knative.
[AWS SNS](https://github.com/triggermesh/knative-lambda-sources/tree/master/awssns) | Active Development | TriggerMesh | Registers for events of the specified AWS SNS endpoint. Brings those events into Knative.
[AWS SQS](https://github.com/triggermesh/knative-lambda-sources/tree/master/awssqs) | Active Development | TriggerMesh | Registers for events of the specified AWS SQS queue. Brings those events into Knative.
[FTP / SFTP](https://github.com/vaikas-google/ftp) | Proof of concept | None | Watches for files being uploaded into a FTP/SFTP and generates events for those.
[Heartbeat](https://github.com/Harwayne/auto-container-source/tree/master/heartbeat-source) | Proof of Concept | None | Uses an in-memory timer to produce events as the specified interval. Uses AutoContainerSource for underlying infrastructure.
[Heartbeats](https://github.com/knative/eventing-contrib/tree/{{< branch >}}/cmd/heartbeats) | Proof of Concept | None | Uses an in-memory timer to produce events at the specified interval.
[K8s](https://github.com/Harwayne/auto-container-source/tree/master/k8s-event-source) | Proof of Concept | None | Brings Kubernetes cluster events into Knative. Uses AutoContainerSource for underlying infrastructure.
[WebSocket](https://github.com/knative/eventing-contrib/tree/{{< branch >}}/cmd/websocketsource) | Active Development | None | Opens a WebSocket to the specified source and packages each received message as a Knative event.

