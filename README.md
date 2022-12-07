# Deploy Kafka on Kubernetes running on Docker Desktop


## Getting Started

## Step1: Clone the repository

```
git clone https://github.com/collabnix/kafka-kubernetes-docker-desktop
```


## Step 2: Deploy Namespace

```
kubectl apply -f 00-namespace.yaml
```

## Step 3. Deploy Zookeeper

```
kubectl apply -f 01-zookeeper.yaml
```

```
kubectl get services -n kafka 
NAME                TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
kafka-service       ClusterIP   10.108.23.106   <none>        9092/TCP         53s
zookeeper-service   NodePort    10.103.75.135   <none>        2181:30181/TCP   3m17s
```

## Step 3. Deploy a Kafka Broker

```
kubectl apply -f 02-kafka.yaml
```


```
kubectl get pods -n kafka
NAME                            READY   STATUS    RESTARTS   AGE
kafka-broker-67c868fc47-rzrzh   1/1     Running   0          30s
zookeeper-654bbcd6cc-p5xfz      1/1     Running   0          2m54s
```

## Step 4. Enable Port Forwarding

```
kubectl port-forward kafka-broker-67c868fc47-rzrzh 9092 -n kafka
Forwarding from 127.0.0.1:9092 -> 9092
Forwarding from [::1]:9092 -> 9092
```

