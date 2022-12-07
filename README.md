# Deploy Kafka on Kubernetes running on Docker Desktop


## Getting Started

## Step 1: Deploy Namespace

```
kubectl apply -f 00-namespace.yaml
```

## Step 2. Deploy Zookeeper

```
kubectl apply -f 01-zookeeper.yaml
```

## Step 3. Deploy a Kafka Broker

```
kubectl apply -f 02-kafka.yaml
```

