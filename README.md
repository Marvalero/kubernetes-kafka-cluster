# kubernetes-kafka-cluster

## Requirements

- Datadog key set in environments/$environment.yaml for monitoring

- `go get github.com/AlexsJones/vortex`

- Also requires Zookeeper https://github.com/AlexsJones/kubernetes-zookeeper-cluster.git


## Example

`kubectl exec kafka-0 -- kafka-topics.sh --create --zookeeper zk-cs.zk.svc.cluster.local:2181 --replication-factor 3 --partitions 1 --topic test`
`
`kubectl exec kafka-0 -- kafka-topics.sh --zookeeper zk-cs.zk.svc.cluster.local:2181 --list`

`kubectl exec kafka-0 -- kafka-console-producer.sh --broker-list zk-hs.zk.svc.cluster.local:9092 --topic test`